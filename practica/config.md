# MongoDB
## Actividad 0
### Notes to Initial Config MongoDB
**Windows**
Open the *cmd* console
```
    cmd.exe
```
Make sure to have this files to start MongoDB shell
> C:\'Programa Files'\MongoDB\Server\4.4\bin\mongod.exe
> C:\'Programa Files'\MongoDB\Server\4.4\bin\mongo.exe

MongoDB bin path
> C:\Program Files\MongoDB\Server\4.4\bin\

How to run *mongod* and *mongo* from anywhere in a command window.
1) Find the MongoDB bin folder.
2) Copy the path to the bin folder, this should be like "C:\Program Files\MongoDB\Server\4.4\bin\"
3) Press Windows key, type "env" to edit the System Environment Variables.
4) On the Advanced tab, edit the Path variable
6) Create “New” path by pasting the copied-path to MongoDB bin folder. Make sure it ends with
    > \

Connect to DB from Compass Client
> mongodb://localhost:27017/?readPreference=primary&appname=MongoDB%20Compass&ssl=false