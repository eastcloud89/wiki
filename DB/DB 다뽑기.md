# Mongo DB 다뽑기
	DBQuery.shellBatchSize = 300 
	db.getCollection('contents').find({})
	db.getCollection('contents').find({},{content:1, _id: 1}).pretty();

	db.getCollection('contents').find({'likes.likeSize':{ $gt: 150 }},{content:1}).sort( {'likes.likeSize': -1 }).pretty();
	db.getCollection('contents').find({},{content:1, 'likes.likeSize': 1}).sort( {'likes.likeSize': -1 }).pretty();

	db.getCollection('contents').find({
            'likes.likeSize':{ $gt: 15 },
            'createdAt':{
                $gte: ISODate("2016-09-01T00:00:00.000Z"),
                $lt: ISODate("2016-10-03T00:00:00.000Z")
             }
    
        
        },{content:1, 'likes.likeSize': 1, 'after.afterContent':1, 'comments.commentInfo.comment':1, bgUrl:1, images:1}).sort( {'likes.likeSize': -1 }).pretty();

	db.getCollection('contents').find({"content":/.*사랑.*/})

[https://docs.mongodb.com/manual/tutorial/project-fields-from-query-results/](참고링크)	
