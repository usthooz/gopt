# gopt
Golang 项目代码自动生成工具

* Types
* Proejct
* ORM
* Controller
* Errors
* Arugments


## Install
```
go get -u -f -d github.com/domego/gopt/...
cd $GOPATH/src/github.com/domego/gopt
make install
```

## gopt Commands
```
Usage: gopt <command> [options]

Commands:

	gen_gin_server	generate gin server code from template
	gen_orm	generate database orm code from template
	gen_gin_api	generate gin controller code from template
	gen_js_api	generate vue-resource code from api template
	gen_api_doc	generate api doc from api template
	version	show version
	help	show help
	gen_types	generate structs code from yaml config file
	gen_errors	generate error_msg.yaml and error constants from yaml config file

Options:

	-types	types config file, default: types.yaml
	-errors	errors config file, default: errors.yaml
	-orm	database config file, default: db.yaml
	-api	gin controller config file, default: api.yaml

```


## Example

- gen_gin_server
```
gopt gen_gin_server -name demo -port 8080
```

- gen_orm
```
gopt gen_orm -orm db.yaml
```

- gen_gin_api
```
gopt gen_gin_api -api api.yaml
```

- gen_js_api
```
gopt gen_js_api
```

- gen_api_doc
```
gopt gen_api_doc
```

- gen_types
```
gopt gen_types -types types.yaml
```

- gen_errors
```
gopt gen_errors -errors errors.yaml
```

## Project Structure
```
.
├── Makefile
├── NAME
├── README.md
├── api
│   ├── gen_types.go
│   └── user
│       ├── controller.go
│       ├── gen_controller.go
│       └── gen_route.go
├── api.yaml
├── app.go
├── bin
│   ├── daemonize-darwin
│   └── daemonize-linux
├── cfg
│   └── config.go
├── config
│   ├── config.yaml
│   └── error_msg.yaml
├── controller
│   └── role
│       ├── controller.go
│       ├── gen_controller.go
│       └── gen_route.go
├── db.yaml
├── doc
│   └── api_doc.md
├── errors
│   └── gen_errors.go
├── errors.yaml
├── fresh.conf
├── gen_types.go
├── main.go
├── model
│   ├── all
│   │   └── all.go
│   └── demo
│       ├── gen_db.go
│       └── gen_user.go
├── router.go
├── service.sh
├── types.yaml
└── webapp
    └── src
        └── api.js

14 directories, 31 files
```

## Run
```
make fresh
```