## Golang

Go, also known as Golang, is an open-source programming language created by Google. It was designed by Robert Griesemer, Rob Pike, and Ken Thompson, and first released in 2009.


Go was developed with simplicity, efficiency, and concurrency in mind. It is known for its clean syntax, ease of use, and speed, making it popular for developing high-performance applications, especially in the cloud computing space, web services, and networking.

### go.mod and go.sum files:

#### go.mod: 
The `go.mod` file defines the module for your Go project. It serves as the configuration file that specifies the project's dependencies, the Go version being used, and other module-related information.
The `go.mod` file defines your project's module name, dependencies, and their required versions.

- go.mod is just like the `package.json` in node.js and `requirements.txt` file in python. but it slighty diff. In node.js `package.json` created automatically while 
go.mod file created by `go mode init` and modified by go developer manually. 


#### go.sum: 
The `go.sum` file is a log of all packages downloaded by the go. sum files are not lock files but a log of all packages downloaded by Go when building a project
- go.sum is just like the `package-lock.json` in node.js.
- for `go.sum` file just run `go mode tidy` to create and update all the dependencies which are define in `go.mod` file.

