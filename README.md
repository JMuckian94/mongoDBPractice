This is a workspace to learn the basics of MongoDB

# AWS Cloud9
- **Download/Install MongoDB client 4.0.6 for Atlas**
- `wget -q https://git.io/fjzf1 -O /tmp/setupmongodb.sh && source /tmp/setupmongodb.sh`


# Old Cloud9
- **Download/Install MongoDB client 4.0.6 for Atlas on old Cloud9**
- `wget -q https://git.io/fh7vV -O /tmp/setupmongodb.sh && source /tmp/setupmongodb.sh`


# Gitpod
- **Connect to Mongo CLI on Gitpod**
- navigate to your MongoDB Clusters Sandbox
- click **"Connect"** button
- select **"Connect with the mongo shell"**
- select **"I do not have the mongo shell installed"**
- choose option: **"Run your connection string in your command line"**
- `mongo "mongodb+srv://<CLUSTER-NAME>.mongodb.net/<DBname>" --username <USERNAME>`
- For this project it is: mongo "mongodb+srv://practicecluster.5cmkt.mongodb.net/celebrities" --username XenoEcho534
- replace all `<angle-bracket>` keys with your own data
- enter password *(will not echo ******** *on screen)*

# If the Mongo Shell is already installed
- Select mongo shell version
- Run your connection string in your command line
- Use this connection string in your application:
mongo "mongodb+srv://practicecluster.5cmkt.mongodb.net/myFirstDatabase" --username XenoEcho534
- Replace myFirstDatabase with the name of the database that connections will use by default. You will be prompted for the password for the Database User, XenoEcho534. When entering your password, make sure all special characters are URL encoded.

#### Clear screen in Mongo Shell:
- `cls`


#### Show all database collections:
- 'show dbs'
- 'use practiceDB'
- `show collections`


#### Assign collection to variable 'coll':
- `coll = db.collection_name`


#### Insert data to collection:
```shell
coll.insert({
    first: "john",
    last: "lennon",
    dob: "09/10/1940",
    gender: "m",
    hair_color: "brown",
    occupation: "beatle",
    nationality: "british"
});
coll.insert({
    first: "eve",
    last: "ryan",
    dob: "19/09/1992",
    gender: "f",
    hair_color: "pink",
    occupation: "developer",
    nationality: "irish"
});
coll.insert({
    first: "martha",
    last: "fenton",
    dob: "15/05/1974",
    gender: "f",
    hair_color: "brown",
    occupation: "manager",
    nationality: "irish"
});
coll.insert({
    first: "neil",
    last: "hanslem",
    dob: "14/07/1983",
    gender: "m",
    hair_color: "blonde",
    occupation: "actor",
    nationality: "british"
});
coll.insert({
    first: "rocky",
    last: "persolm",
    dob: "19/12/1994",
    gender: "f",
    hair_color: "black",
    occupation: "activist",
    nationality: "american"
});
```

#### Find all documents in collection:
- `coll.find();`


#### Find all documents with gender == "f":
- `coll.find({gender: "f"});`


#### Find all documents with gender == "f" AND nationality == "british":
- `coll.find({gender: "f", nationality: "british"});`


#### Find all documents with gender == "f" AND nationality == "american" OR "irish":
- `coll.find({gender: "f", $or: [{nationality: "american"}, {nationality: "irish"}]});`


#### Find all documents with gender == "f" AND nationality == "american" OR "irish", then sort by nationality (ascending):
- `coll.find({gender: "f", $or: [{nationality: "american"}, {nationality: "irish"}]}).sort({nationality: 1});`


#### Find all documents with gender == "f" AND nationality == "american" OR "irish", then sort by nationality (descending):
- `coll.find({gender: "f", $or: [{nationality: "american"}, {nationality: "irish"}]}).sort({nationality: -1});`