## 1 - Instalar Go no wsl2 e não esquecer de fazer: 

```
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOROOT:$GOPATH:$GOBIN
```

## 2 - No console
```
go mod init github.com/exemple;
go get google.golang.org/protobuf/cmd/protoc-gen-go;
go install
```

## 3 - No código fonte dos arquivos .proto
### | na parte `option go_package` colocar  `./` e não apenas `.` para informar "./;pb", pois o go.mod está no diretório acima.

## Rodar comando para converter os arquivos .porto para Golang
```
protoc --proto_path=proto proto/*.proto --go_out=pb
```