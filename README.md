// Design database for Zen class programme
// users
// codekata
// attendance
// topics
// tasks
// company_drives
// mentors

// show dbs - Is used to show the database list. 

// Create a database using the command

// 1. To create the database use the command - use topics-data
// 2. to insert into the database use the following 
// command -db.topics.insertMany({}) to insert all the data 


// 1. Find all the topics and tasks which are thought in the month of October

db.topics.find({
    month: {
      "$eq": "October"
    }
  })

// 2. Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020
// use the command db.companydrives.insertMany({}) to insert data in the collection 

db.companydrive.find({
    "$and": [
      {
        "date": {
          "$gt": "15-10-2020"
        }
      },
      {
        "date": {
          "$lt": "31-10-2020"
        }
      }
    ]
  })

//   result 

//   [

//     {
//       "_id": ObjectId("5a934e000102030405000002"),
//       "company": "Ernser - Thompson",
//       "date": "16-10-2020",
//       "id": "3",
//       "students": "Duane O'Keefe"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000003"),
//       "company": "Moen - Harris",
//       "date": "17-10-2020",
//       "id": "4",
//       "students": "Lance Carroll"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000004"),
//       "company": "Wintheiser LLC",
//       "date": "18-10-2020",
//       "id": "5",
//       "students": "Samuel Hirthe"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000005"),
//       "company": "Heidenreich - Beer",
//       "date": "19-10-2020",
//       "id": "6",
//       "students": "Darlene Cormier"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000006"),
//       "company": "Boehm, Kreiger and Pagac",
//       "date": "20-10-2020",
//       "id": "7",
//       "students": "Francis D'Amore"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000007"),
//       "company": "Kuhn and Sons",
//       "date": "21-10-2020",
//       "id": "8",
//       "students": "Eula Franecki"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000008"),
//       "company": "Corkery, Romaguera and Wiza",
//       "date": "22-10-2020",
//       "id": "9",
//       "students": "Rafael Nienow V"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000009"),
//       "company": "Johnson LLC",
//       "date": "23-10-2020",
//       "id": "10",
//       "students": "Hugo Witting"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000a"),
//       "company": "Yost - Hamill",
//       "date": "24-10-2020",
//       "id": "11",
//       "students": "Lester Strosin"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000b"),
//       "company": "Stroman Inc",
//       "date": "25-10-2020",
//       "id": "12",
//       "students": "Rudy Maggio"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000c"),
//       "company": "Kohler - Greenfelder",
//       "date": "26-10-2020",
//       "id": "13",
//       "students": "Virginia Fritsch"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000d"),
//       "company": "Conn and Sons",
//       "date": "27-10-2020",
//       "id": "14",
//       "students": "Kristin Hayes"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000e"),
//       "company": "Welch, Pouros and Wunsch",
//       "date": "28-10-2020",
//       "id": "15",
//       "students": "Marty Gibson"
//     },
//     {
//       "_id": ObjectId("5a934e00010203040500000f"),
//       "company": "Prohaska Inc",
//       "date": "29-10-2020",
//       "id": "16",
//       "students": "Charlie Durgan"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000010"),
//       "company": "Kautzer, Yundt and Mraz",
//       "date": "30-10-2020",
//       "id": "17",
//       "students": "Miss Charlotte Haley"
//     },
//     {
//       "_id": ObjectId("5a934e000102030405000013"),
//       "company": "Quigley - Abshire",
//       "date": "2-11-2020",
//       "id": "20",
//       "students": "Kerry Kreiger I"
//     }
//   ]



// 3. Find all the company drives and students who are appeared for the placement.
db.companydrive.find({},
    {
      company: 1,
      students: 1
    })

// 4. Find the number of problems solved by the user in codekata
db.user.find({})


// 5. Find all the mentors with who has the mentee's count more than 15
db.mentors.find({
    "mentees": {
      "$gt": 15
    }
  },
  {
    mentor: 1
  })

// 6. Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020
db.users.find({})
