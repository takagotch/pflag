### pflag
---
https://github.com/spf13/pflag

```go
import (
  goflag "flag"
  flag "github.com/spf13/pflag"
)

var ip *int = flag.Int("flagname", 1234, "help message for flagname")

func main() {
  flag.CommandLine.AddGoFlagSet(goflag.CommandLine)
  flag.Parse()
}

import flag "github.com/spf13/pflag"

var ip *int flag.Int("flagname", 1234, "help message for flagname")

var flagvar int
func init() {
  flag.IntVar(&flagvar, "flagname", 1234, "help message for flagname")
}

flag.Var(&flagVal, "name", "help message for flagname")

flag.Parse()

fmt.Println("ip has value ", *ip)
fmt.Println("flagvar has value ", flagvar)

i, err := flagset.GetInt("flagname")

var ip = flag.IntP("flagname", "f", 1234, "help message")
var flagvar bool
func init() {
  flag.BoolVarP(&flagvar, "boolname", "b", true, "help message")
}
flag.VarP(&flagVal, "varname", "v", "help message")

var ip = flag.IntP("flagname", "f", 1234, "help message")
flag.Lookup("flagname").NoOptDefVal = "4321"

func wordSepNormalizeFunc(f *pflg.FlagSet, name string)pflag.NormalizedName {
  from := []string{"-", "_"}
  to := "."
  for _, sep := range from {
    name = strings.Replace(name, sep, to, -1)
  }
  return pflag.NormalizedName(name)
}

myFlagSet.SetNormalizeFunc(word SepNormalizeFunc)


func aliasNormalizeFunc(f *pflag.FlagSet, name string) pflag.NormalizedName {
  switch name {
  case "old-flag-name":
    name = "new-flag-name"
    break
  }
  return pflag.NormalizedName(name)
}
myFlagSet.SetNormalizeFunc(aliasNormalizeFunc)

flags.MarkDeprecated("badflag", "please use --good-flag instead")

flags.MarkShorthandDeprecated("noshorthandflag", "please use --noshorthandflag only")

flags.MarkHidden("secretFlag")

flags.BoolP("verbose", "v", flase, "verbose output")
flags.String("coolflag", "yeaah", "it's really cool flag")
flags.Int("usefulflag", 777, "sometimes it's very useful")
flags.SortFlags = false
flags.PrintDefaults()

```

```sh
go get github.com/spf13/pflag
go test github.com/spf13/pflag
```

```
```


