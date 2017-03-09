# vscode GO 環境構築

Go言語のインストールに必要な手順メモ  
必要なモノ  
* [go](https://golang.org/dl/)
* [vscode](https://code.visualstudio.com/)
    * [Go for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=lukehoban.Go)
* [git](https://git-scm.com/)

## go 設定
* Ver.1.8を選択  
* msiインストーラーに沿ってやればおｋ  
* Ver.1.8ならGOPATH、GOROOTは自動で設定してくれる  

インストール確認  

```bash
go version
```

## vsdode 設定

諸々インストール。  

```bash
go get -u -v github.com/nsf/gocode
go get -u -v github.com/rogpeppe/godef
go get -u -v github.com/zmb3/gogetdoc
go get -u -v github.com/golang/lint/golint
go get -u -v github.com/lukehoban/go-outline
go get -u -v sourcegraph.com/sqs/goreturns
go get -u -v golang.org/x/tools/cmd/gorename
go get -u -v github.com/tpng/gopkgs
go get -u -v github.com/newhook/go-symbols
go get -u -v golang.org/x/tools/cmd/guru
go get -u -v github.com/cweill/gotests/...
```

ファイル＞基本設定＞設定 よりsetting.jsonを設定。  
```json
{
    "go.buildOnSave": true,
    "go.lintOnSave": true,
    "go.vetOnSave": true,
    "go.buildTags": "",
    "go.buildFlags": [],
    "go.lintTool": "golint",
    "go.lintFlags": [],
    "go.vetFlags": [],
    "go.testOnSave": false,
    "go.coverOnSave": false,
    "go.useCodeSnippetsOnFunctionSuggest": false,
    "go.formatOnSave": true, 
    "go.formatTool": "goreturns",
    "go.formatFlags": [],
    "go.goroot": "/**user goroot**",
    "go.gopath": "/**user gopath**",
    "go.inferGopath": false,
    "go.gocodeAutoBuild": false
}
```

goroot、gopathは以下のコマンドで確認可能。  

```bash
go env GOROOT

go env GOOATH
```

動作確認
```bash
go run hello.go
```
