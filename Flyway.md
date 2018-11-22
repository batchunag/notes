#Connect using url
flyway -user=$(whoami) -password= -url=jdbc:mysql://127.0.0.1:3306/db

flyway info

flyway migrate

flyway repair

