# difflib

>使用方法：
    
    package main

    import (
        "fmt"
        "github.com/xuyingquan/difflib"
    )

    func main() {
        src := "[default]\nuser=test\npassword=123456\n[db]\nipaddr=172.30.40.20\nport=3306\n"
        dest := "[default]\nuser=test\npassword=123456\n[db]\nipaddr=172.30.40.21\nport=3306\n"
        diff := difflib.UnifiedDiff{
            A:        difflib.SplitLines(src),
            B:        difflib.SplitLines(dest),
            FromFile: "/path/src.conf",
            ToFile:   "/path/dest.conf",
            Context:  3,
        }
        text, _ := difflib.GetUnifiedDiffString(diff)
        fmt.Printf(text)
    }
