# gacha

オンラインイベント[学生向け／オンライン実施】Step up Go for Students 3-4](https://mercari.connpass.com/event/213552/?utm_campaign=event_participate_to_follower&utm_source=notifications&utm_medium=twitter)で使用したパッケージです。

## Example Code

```
package main

import (
	"fmt"

	"github.com/TeppeiSudo/gacha"
)

func main() {
	p := gacha.NewPlayer(10, 100)
	n := inputN(p)
	results, summary := gacha.DrawN(p, n)

	fmt.Println(results)
	fmt.Println(summary)
}

func inputN(p *gacha.Player) int {

	max := p.DrawableNum()
	fmt.Printf("ガチャを引く回数を入力してください（最大:%d回）\n", max)

	var n int
	for {
		fmt.Print("ガチャを引く回数>")
		fmt.Scanln(&n)
		if n > 0 && n <= max {
			break
		}
		fmt.Printf("1以上%d以下の数を入力してください\n", max)
	}

	return n
}
```

## How to install

```
go get Github.com/TeppeiSudo/gacha@v0.0.1
```