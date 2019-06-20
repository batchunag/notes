#Check if mongod version is above 4.0.0
	> mongod --version
	Don't know why but 4.0.2 works
>If not remove old version and install 4.0.2
	apt-get purge mongo*
	install here https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/
	

#Some note: changing mongodb path
https://medium.com/@paulrohan/how-to-install-mongodb-on-ubuntu-15-04-and-15-10-9301e53a0d94

#Start service
sudo service mongod start
Confirm by tailing: 
tail -f /var/log/mongodb/mongod.log

#Restart
sudo service mongod restart

#18.04 Unit mongod.service not found.
mongod -->  IllegalOperation: Attempted to create a lock file on a read-only directory: /data/db, terminating

> System config
vim /lib/systemd/system/mongodb.service


#Select fields
`db.student.find({}, {roll:1})`
https://stackoverflow.com/questions/25589113/how-to-select-a-single-field-for-all-documents-in-a-mongodb-collection

PojoCodecProvider can be used only after Mongodb 3.5

#CustomEncoder
```java
override fun encode(writer: BsonWriter, value: MyClass, encoderContext: EncoderContext) {
//Attempt 1:Failed
//        writer.writeString(value)
//Attempt 2:Failed
//        writer.writeString(mapper.convertValue(value, BasicDBObject::class.java).toString())
//Attempt 3:Failed
//        val data = mapper.writeValueAsBytes(value)
//        rawBsonDocumentCodec.encode(writer, RawBsonDocument(data), encoderContext)
//Attempt 4:Success
    val json = mapper.writeValueAsString(value)
    rawBsonDocumentCodec.encode(writer, RawBsonDocument.parse(json), encoderContext)
}
```

#Codec for Java, Kotlin without Lombok
Following is necessary esp with Mongodb 3.4
Default codec is provided since 3.5, so following custom codec can be used till the update.

```java
class MyCustomPOJOCodec : Codec<MyCustomPOJO> {
    val mapper = ObjectMapper().registerModule(KotlinModule())
    val rawBsonDocumentCodec = RawBsonDocumentCodec()
    val bsonDocumentCodec = BsonDocumentCodec()

    override fun encode(writer: BsonWriter, value: MyCustomPOJO, encoderContext: EncoderContext) {
        val json = mapper.writeValueAsString(value)
        rawBsonDocumentCodec.encode(writer, RawBsonDocument.parse(json), encoderContext)
    }

    override fun decode(reader: BsonReader, decoderContext: DecoderContext): MyCustomPOJO {
//        val document = rawBsonDocumentCodec.decode(reader, decoderContext)
        val document = bsonDocumentCodec.decode(reader, decoderContext)
       document.remove("_id") //This was actually not necessary because _id can be custom String.
        return mapper.readValue(document.toString(), MyCustomPOJO::class.java)
//        return mapper.readValue(reader.readString(), MyCustomPOJO::class.java)
//        val document = rawBsonDocumentCodec.decode(reader, decoderContext)
//        return mapper.readValue(document.getByteBuffer().array(), MyCustomPOJO::class.java)
    }

    override fun getEncoderClass(): Class<MyCustomPOJO> {
        return MyCustomPOJO::class.java
    }
}
```

