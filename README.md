**1.create data base**
```
use company
switched to db company

```
**2.create collection**
```
db.createCollection("client")
{ ok: 1 }
```
**3.insert Many**
```
db.client.insertMany([{name:"pirani",age:22,address:{street:"rathnapuram",city:"kilinochi",province:"north"},cashcost:"50000",balance:"20000"},{name:"nilaxsh",age:28,address:{street:"kanthamurukesanar lane",city:"point pedro",province:"north"},cashcost:"10000",balance:"20000"},{name:"janany",age:34,address:{street:"a9hotal lane",city:"wellawatta",province:"colombo"},cascost:"30000",balance:"5000"}])


{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("655a1c7923820642fc5cee62"),
    '1': ObjectId("655a1c7923820642fc5cee63"),
    '2': ObjectId("655a1c7923820642fc5cee64")
  }
}
```
**4.insert One**
```
db.client.insertOne({name:"kabish",address:{street:"amastreet",city:"wellawatta",province:"colombo"},cashcost:"5000",balance:"1000"})
{
  acknowledged: true,
  insertedId: ObjectId("655a1e1723820642fc5cee65")
}
```
**5.find**
```
db.client.find()
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**6.limit**
```
db.client.find().limit(2)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**7.sort +**
```
db.client.find().sort({name:1}).limit(3)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**8.sort -**
```
db.client.find().sort({name:-1}).limit(3)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**9.sort**
```
db.client.find().sort({name:-1}).limit(3)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**10.sort**
 db.client.find().sort({age:1,name:-1}).limit(3)
 ```
[
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**11.insertmany**
```
db.client.insertMany([{name:"saru",address:"mannar",cashcost:"8000",balance:"500"},{name:"mathu",address:"kandy",cashcost:"2000",balance:"100"}]){
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("655a251b23820642fc5cee66"),
    '1': ObjectId("655a251b23820642fc5cee67")
  }
}
company> db.client.find().sort({age:1}).limit(3)
[
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**12.**
```
db.client.find().sort({age:1,name:-1}).limit(3)
[
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**13**
```
db.client.find().sort({age:-1,name:1}).limit(3)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  }
]
```
**14 skip**
```
db.client.find().skip(1).limit(2)
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  }
]
```
**15**
```
db.client.find({age:22})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  }
]
```
**16**
```
db.client.find({name:"kabish"})
[
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**17**
```
db.client.find({name:"pirani"},{name:1,age:1})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22
  }
]
```
**18**
```
 db.client.find({name:"pirani"},{name:1,age:1,_id:0})
[ { name: 'pirani', age: 22 } ]
```

**11**
```
db.client.find({name:"pirani"},{age:0})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  }
]
```
**12 eq**
```
db.client.find({name: {$eq:"pirani"}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  }
]
```
**13 no equal**
```
 db.client.find({name: {$ne:"pirani"}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  }
]
```
**14 greater than**
```
db.client.find({age:{$gt:24}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  }
]
```
**15.greater than equal**
```
db.client.find({age:{$gte:28}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  }
]
```
**16.less than equal**
```
db.client.find({age:{$lte:28}})
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**17less than**
```
db.client.find({age:{$lt:30}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**18 in quary**
```
db.client.find({name:{$in:["kabish","nilaxsh"]}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**19**
```
db.client.find({name:{$in:["kabish","sh"]}})
[
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```
**20 no in quary**
```
 db.client.find({name:{$nin:["kabish","nilaxsh"]}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  }
]
```
**21 exists true**
```
 db.client.find({age:{$exists:true}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  }
]
```
**22 exists false**
```
db.client.find({age:{$exists:false}})
[
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  }
]
```
**23**
```
db.client.insertOne({age:null,cashcost:"3000",balance:"10"})
{
  acknowledged: true,
  insertedId: ObjectId("655a3aa310b488667ab75d3f")
}
```
**24**
```
db.client.find({age:{$exists:false}})
[
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  }
]
```
**25**
```
db.client.find({age:{$exists:true}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a3aa310b488667ab75d3f"),
    age: null,
    cashcost: '3000',
    balance: '10'
  }
]
```
**26**
```
db.client.find({age:{$gte:24,$lte:30}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**27**
```
db.client.find({age:{$gte:24,$lte:30},name:"nilaxsh"})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
company> db.client.find({$and:[{age:28},{name:"nilaxsh"}]})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**28**
```
db.client.find({$or:[{city:"colombo"},{name:"nilaxsh"}]})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**29**
```
db.client.find({$or:[{age:28},{name:"nilaxsh"}]})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**30**
```
 db.client.find({$or:[{age:22},{name:"nilaxsh"}]})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  }
]
```
**30**
```
db.client.find({age:{$not:{$lte:28}}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  },
  {
    _id: ObjectId("655a3aa310b488667ab75d3f"),
    age: null,
    cashcost: '3000',
    balance: '10'
  }
]
```
**31**
```
db.client.find({age:{$not:{$gte:28}}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  },
  {
    _id: ObjectId("655a3aa310b488667ab75d3f"),
    age: null,
    cashcost: '3000',
    balance: '10'
  }
]
```
**33**
```
db.client.find({$expr:{$gt:["cashcost","balance"]}})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 22,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee63"),
    name: 'nilaxsh',
    age: 28,
    address: {
      street: 'kanthamurukesanar lane',
      city: 'point pedro',
      province: 'north'
    },
    cashcost: '10000',
    balance: '20000'
  },
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee66"),
    name: 'saru',
    address: 'mannar',
    cashcost: '8000',
    balance: '500'
  },
  {
    _id: ObjectId("655a251b23820642fc5cee67"),
    name: 'mathu',
    address: 'kandy',
    cashcost: '2000',
    balance: '100'
  },
  {
    _id: ObjectId("655a3aa310b488667ab75d3f"),
    age: null,
    cashcost: '3000',
    balance: '10'
  }
]
```
**34.count documents**
```
 db.client.countDocuments()
7
```
**35**
```
db.client.countDocuments({age:{$gt:24}})
2
```
**36 ubdate**
```
db.client.updateOne({age:22},{$set:{age:21}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```
**37**
```
db.client.find({age:21})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee62"),
    name: 'pirani',
    age: 21,
    address: { street: 'rathnapuram', city: 'kilinochi', province: 'north' },
    cashcost: '50000',
    balance: '20000'
  }
]
company> db.client.find({"address.province":"colombo"})
[
  {
    _id: ObjectId("655a1c7923820642fc5cee64"),
    name: 'janany',
    age: 34,
    address: { street: 'a9hotal lane', city: 'wellawatta', province: 'colombo' },
    cascost: '30000',
    balance: '5000'
  },
  {
    _id: ObjectId("655a1e1723820642fc5cee65"),
    name: 'kabish',
    address: { street: 'amastreet', city: 'wellawatta', province: 'colombo' },
    cashcost: '5000',
    balance: '1000'
  }
]
```










