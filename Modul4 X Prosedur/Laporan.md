<h1 align="center" > Laporan Praktikum Modul  4 X Prosedur</h1>


<p align="center ">Satria Adhi Sadarma - 103112400273<p/>
## Soal latihan modul 4


soal 1
```go
package main

  

import (

    "fmt"

)

  
  

func factorial(n int) int {

    hasil := 1

    for i := 2; i <= n; i++ {

        hasil *= i

    }

    return hasil

}

  

func permutation(n, r int) (hasil int, penjelasan string) {

    nFact := factorial(n)

    nrFact := factorial(n - r)

    hasil = nFact / nrFact

  

    penjelasan = fmt.Sprintf("P(%d,%d) = %d!/%d! = %d/%d = %d", n, r, n, n - r, nFact, nrFact, hasil)

  

    return

}

  

func combination(n, r int) (hasil int, penjelasan string) {

    nFact := factorial(n)

    rFact := factorial(r)

    nrFact := factorial(n - r)

  

    hasil = nFact / (rFact * nrFact)

  

    penjelasan = fmt.Sprintf("C(%d,%d) = %d!/(%d!×%d!) = %d/(%d×%d) = %d", n, r, n, r, n - r, nFact, rFact, nrFact, hasil)

  

    return

}

  

func main() {

    var a, b, c, d int

  

    fmt.Scan(&a, &b, &c, &d)

  

    if a < c || b < d {

        fmt.Println("Input tidak memenuhi syarat a >= c dan b >= d")

        return

    }

  

    Pac, penjelasanP1 := permutation(a, c)

    Cac, penjelasanC1 := combination(a, c)

  

    Pbd, penjelasanP2 := permutation(b, d)

    Cbd, penjelasanC2 := combination(b, d)

  

    fmt.Println(Pac, Cac)

    fmt.Println(Pbd, Cbd)

  

    fmt.Println(penjelasanP1)

    fmt.Println(penjelasanC1)

    fmt.Println(penjelasanP2)

    fmt.Println(penjelasanC2)

}
```

output
![](soal1modul4.png)


soal 2
```go
package main

  

import (

    "fmt"

    "strings"

)

  

const MAX_WAKTU = 301

  
  

func hitungSkor(waktu [8]int, soal *int, skor *int) {

    *soal = 0

    *skor = 0

  

    for i := 0; i < 8; i++ {

        if waktu[i] < MAX_WAKTU {

            *soal++

            *skor += waktu[i]

        }

    }

}

  

func main() {

    var (

        nama        string

        waktu       [8]int

        pemenang    string

        maxSoal     int

        minSkor     int

        jumlahSoal  int

        totalWaktu  int

    )

  

    minSkor = 99999

  

    for {

        fmt.Scan(&nama)

  

        if strings.ToLower(nama) == "selesai" {

            break

        }

  

        for i := 0; i < 8; i++ {

            fmt.Scan(&waktu[i])

        }

  

        hitungSkor(waktu, &jumlahSoal, &totalWaktu)

  

        if jumlahSoal > maxSoal || (jumlahSoal == maxSoal && totalWaktu < minSkor) {

            pemenang = nama

            maxSoal = jumlahSoal

            minSkor = totalWaktu

        }

    }

  

    fmt.Println(pemenang, maxSoal, minSkor)

}
```

output
![](soal2modul4.png)


soal 3
```go
package main

  

import "fmt"

  

func cetakDeret(n int) {

    for n != 1 {

        fmt.Printf("%d ", n)

        if n%2 == 0 {

            n = n / 2

        } else {

            n = 3*n + 1

        }

    }

  

    fmt.Printf("%d\n", n)

}

  

func main() {

    var n int

    fmt.Scan(&n)

  

    cetakDeret(n)

}
```


output
![](soal3modul4.png)

