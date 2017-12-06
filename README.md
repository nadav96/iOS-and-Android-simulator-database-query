# iOS-and-Android-simulator-database-query
A tool that given the simulator id, app's bundle id and database name, allow you to query the database, and update it.

## Setup
Just copy the files to /usr/local/bin, and give them execute permissions.
```bash
sudo chmod +x ./*
sudo cp ./* /usr/local/bin/
```

## Usage
### iOS

```bash
sqlios {device-id} {package-name} {database-name} {query}
```

**device id** - the simulator id, can be fetched with ``` instruments -s devices ```

**package name** - the app package name

**database name** - the database which the tool will query against

**query** - the sql statment

For example:
```bash
sqlios 7703F5CD-B023-41C9-916F-B7C6B783104C com.demoapp.hello demo.db "select * from Sites"
```

If you don't know the database name, you can remove the database name and query paramaters, and the tool will list the available db files for the given package.
```bash
sqlios 7703F5CD-B023-41C9-916F-B7C6B783104C com.demoapp.hello
```

### Android
```bash
sqlAndroid {package name} {database name} {sql query}
```

* Please note on Android, the tool will work only if there is **1 simulator running**. You can view this with: ```adb devices```

Example:
```bash
sqlAndroid com.demoapp.hello demo.db "select * from Sites"
```
