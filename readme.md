db.students.find({scores: {$elemMatch: {score: {$gt: 87, $lt: 93}}}}).pretty()

db.students.aggregate([
    {
        $unwind: "$scores"
    },
    {
        $match: {
            "scores.type" : 'exam',
            "scores.score" : {$gt: 90}
        }
    }
])

db.students.updateMany({name: "Dusti Lemmond"}, {$set: {'accepted': true}})
