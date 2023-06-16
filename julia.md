# Cara Install Julia di Ubuntu 20.04

this is a file whithout a heading

```markdown
Pengertian Julia
```

Julia adalah bahasa pemrograman open source tingkat tinggi.

```markdown
# Install Julia
```

```markdown
wget https://julialang-s3.julialang.org/bin/linux/x64/1.9/julia-1.9.1-linux-x86_64.tar.gz
tar zxvf julia-1.9.1-linux-x86_64.tar.gz
```

Buatlah sebuah direktori baru untuk menyimpan Julia dan Ekstrak dengan menggunakan `tar.gz` file:

```markdown
sudo mkdir /opt/julia
sudo tar xf julia.tar.gz --strip-components=1 -C /opt/julia
```

Di `/usr/local/bin` direktori kita dapat membuat tautan simbolis ke perintah yang terletak di `bin` direktori.

```markdown
sudo ln -s /opt/julia/bin/* /usr/local/bin
```

Sekarang Julia akan tersedia untuk semua pengguna sebagai perintah di seluruh sistem.
Anda dapat memeriksa versi Julia :

```markdown
julia --version
```

File `tar.gz` tidak lagi di perlukan, hapus :

```markdown
rm -rf julia.tar.gz
```

```markdown
# Menguji Julia
```

Buat file `main.jl`:

```markdown
nano main.jl
```

Keudian tambahkan baris kode berikut ke file Julia yang sudah kita buat:

```markdown
println("Hello world!)
```

Jalankan skrip yang sudah kita buat dengan menggunakan perintah berikut:

```markdown
julia main.jl
```

```markdown
# Copot pemasangan Julia
```

Jika anda ingin menghapus Julia sepenuhnya, hapus direktori instalasi:

```markdown
sudo rm -rf /opt/julia
```

Hapus tautan simbolis dengan perintah sebagai berikut:

```markdown
sudo find /usr/local/bin -lname '/opt/julia/bin/*' -delete
```
