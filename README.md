# mongoAssignment1


let newBlog = 	{
	 "createdAt": new ISODate("2022-09-20T15:07:41.214Z"),
	 "title": "new new",
	 "text": "Nulla expedita libero ut accusantium vitae repellat et. Accusantium ipsa expedita ratione harum provident quia totam. Dicta facilis dicta saepe et. Est et delectus veritatis nihil. Magnam dolor iste perspiciatis officia blanditiis possimus.\nTotam alias corrupti doloribus. Nihil laboriosam expedita omnis nihil. Eos delectus nulla sit magni aut quae distinctio deserunt.\nAutem et aliquam quasi nam. Vero enim ullam voluptas ut quidem libero rerum. Nam omnis illo voluptatem non tempore ipsum. Qui nulla fugiat rerum.",
	 "author": "Jim Davis",
	 "lastModified": new Date(),
	 "categories": ["garfield", "green town", "silly"],
	 "id": "4a571289-6d5c-4300-9814-53c6e1237d84",
	 "objectId": 11
	}
	
// insert the blog list

db.blogs.insertMany(blogs)

// insert the new blog	

db.blogs.insertOne(newBlog)

// find a blog by the author

db.blogs.find({
    author: "Alfred Davis"
})

// find all blogs with objectId greater than 5

db.blogs.find( {
    objectId: {
        $gt: 5
    }
})

// find all blogs created after april 1, 2022

db.blogs.find({
    createdAt: {
        $gt: ISODate('2022-04-01')
    }
})

// find all blogs where lastModified does not exist

db.blogs.find({ lastModified : {$exists:false}})

// find all blogs where lastModified does not exist 

db.blogs.find({createdAt : {$type: "date"}})

// find all blogs where lastModified does not exist and createdAt type == date
db.blogs.find({ lastModified : {$exists:false}, createdAt : {$type: "date"} })

// find a blog using specific phrase using regex in the text

db.blogs.find({
    "text": {$regex: /new/}
})

// find all blogs that have "qui" in the categories array

db.blogs.find({
    categories : {$regex: /qui/}
})