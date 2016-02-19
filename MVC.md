MVC form 
адилхан name.тэй field үүд бол Array хэлбэрээр controller дээр ирнэ.

http://geekswithblogs.net/rgupta/archive/2014/06/25/combining-jquery-form-serialize-and-json.stringify-when-doing-ajax-post.aspx
Энд hidden input.ээр дамжуулж утга авах аргыг бичсэн байна.

#MVC Linked query

	DB.STAFF_INFO.Where(staff => ! DB.JOBS_REQUEST.Select(request => request.Jobs_Client_ID).Contains(staff.id))
	db.STAFF_HISTORY.RemoveRange(db.STAFF_HISTORY.Where(x => x.ID == id))
