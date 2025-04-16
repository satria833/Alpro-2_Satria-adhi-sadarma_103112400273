
<h1 align="center" > Laporan Praktikum Modul  4 X PENCARIAN NILAI EKSTRIM PADA HIMPUNAN DATA</h1>
<p align="center ">Satria Adhi Sadarma - 103112400273<p/>
## Soal latihan modul 10

soal 1
```go
   package main

  

import (

    "fmt"

)

  

func main() {

    var N int

    fmt.Print("Masukkan jumlah anak kelinci: ")

    fmt.Scan(&N)

  
  

    if N <= 0 || N > 1000 {

        fmt.Println("Jumlah anak kelinci harus antara 1 sampai 1000")

        return

    }

  

    berat := make([]float64, N)

  

    fmt.Println("Masukkan berat anak kelinci:")

    for i := 0; i < N; i++ {

        fmt.Scan(&berat[i])

    }

  

    minBerat := berat[0]

    maxBerat := berat[0]

  

    for i := 1; i < N; i++ {

        if berat[i] < minBerat {

            minBerat = berat[i]

        }

        if berat[i] > maxBerat {

            maxBerat = berat[i]

        }

    }

  

    fmt.Printf("Berat terkecil: %.2f\n", minBerat)

    fmt.Printf("Berat terbesar: %.2f\n", maxBerat)

}

```

output
![](output/soal1Modul10.png) 


soal2
```go
package main

  

import (

    "fmt"

)

  

func main() {

    var x, y int

    fmt.Print("Masukkan jumlah ikan (x) dan kapasitas wadah (y): ")

    fmt.Scan(&x, &y)

  

    if x <= 0 || x > 1000 || y <= 0 {

        fmt.Println("Input tidak valid. x harus antara 1-1000 dan y > 0.")

        return

    }

  

    ikan := make([]float64, x)

    fmt.Println("Masukkan berat ikan:")

    for i := 0; i < x; i++ {

        fmt.Scan(&ikan[i])

    }

  

    jumlahWadah := (x + y - 1) / y

    totalBeratPerWadah := make([]float64, jumlahWadah)

  

    for i := 0; i < x; i++ {

        idxWadah := i / y

        totalBeratPerWadah[idxWadah] += ikan[i]

    }

  

    fmt.Println("Total berat per wadah:")

    for _, berat := range totalBeratPerWadah {

        fmt.Printf("%.2f ", berat)

    }

    fmt.Println()

  

    var total float64

    for _, berat := range totalBeratPerWadah {

        total += berat

    }

    rataRata := total / float64(jumlahWadah)

  

    fmt.Printf("Rata-rata berat per wadah: %.2f\n", rataRata)

}

```

output
![](output/soal2Modul10.png)

soal 3
```go
package main

  

import (

    "fmt"

)

  

type arrBalita [100]float64

  

func hitungMinMax(data arrBalita, n int, bMin, bMax *float64) {

    *bMin = data[0]

    *bMax = data[0]

  

    for i := 1; i < n; i++ {

        if data[i] < *bMin {

            *bMin = data[i]

        }

        if data[i] > *bMax {

            *bMax = data[i]

        }

    }

}

  
  

func rerata(data arrBalita, n int) float64 {

    var total float64 = 0

    for i := 0; i < n; i++ {

        total += data[i]

    }

    return total / float64(n)

}

  

func main() {

    var berat arrBalita

    var n int

  

    fmt.Print("Masukan banyak data berat balita : ")

    fmt.Scan(&n)

  

    for i := 0; i < n; i++ {

        fmt.Printf("Masukan berat balita ke-%d: ", i+1)

        fmt.Scan(&berat[i])

    }

  

    var min, max float64

    hitungMinMax(berat, n, &min, &max)

    rata := rerata(berat, n)

  

    fmt.Printf("Berat balita minimum: %.2f kg\n", min)

    fmt.Printf("Berat balita maksimum: %.2f kg\n", max)

    fmt.Printf("Rerata berat balita: %.2f kg\n", rata)

}

```

output
![](output/soal3Modul10.png)

