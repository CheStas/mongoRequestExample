1. `db.students.find({scores: {$elemMatch: {score: {$gt: 87, $lt: 93}}}}).pretty()`

2. `db.students.aggregate([
    {
        $unwind: "$scores"
    },
    {
        $match: {
            "scores.type" : 'exam',
            "scores.score" : {$gt: 90}
        }
    }
])`

3. `db.students.updateMany({name: "Dusti Lemmond"}, {$set: {'accepted': true}})`
