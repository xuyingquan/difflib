# difflib

>使用方法：
    package main

    import (
      "fmt"
      "github.com/xuyingquan/difflib"
    )

    func main() {
      diff := difflib.UnifiedDiff{
        A:        difflib.SplitLines("[default]\nuser=test\npassword=123456\n[db]\nipaddr=172.30.40.20\nport=3306\n"),
        B:        difflib.SplitLines("[default]\nuser=test\npassword=123456\n[db]\nipaddr=172.30.40.21\nport=3306\n"),
        FromFile: "src",
        ToFile:   "dest",
        Context:  3,
      }
      text, _ := difflib.GetUnifiedDiffString(diff)
      fmt.Printf(text)
    }
