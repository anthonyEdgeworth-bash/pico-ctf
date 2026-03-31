## RETO
Rust fixme 1
## DESCRIPCION
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
## SOLUCION


"picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}"


┌──(kali㉿kali)-[~/Downloads/fixme1]
└─$ cargo run
    Updating crates.io index
  Downloaded crossbeam-deque v0.8.5
  Downloaded xor_cryptor v1.2.3
  Downloaded either v1.13.0
  Downloaded crossbeam-utils v0.8.20
  Downloaded crossbeam-epoch v0.9.18
  Downloaded rayon-core v1.12.1
  Downloaded rayon v1.10.0
  Downloaded 7 crates (379.2KiB) in 20.64s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B    Building [=>                          ] 1/12: rayon-core(bu   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/Downloads/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 44.87s
     Running `target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

## NOTAS ADICIONALES
**XOR Decryption:** El código utiliza una operación lógica XOR entre los valores hexadecimales y la clave repetida `"CSUCKS"`. Es un método de cifrado simétrico donde aplicar la misma operación dos veces devuelve el mensaje original.
## REFERENCIAS