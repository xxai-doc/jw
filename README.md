<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Disaranake nginstal nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dhisik, banjur `direnv allow` sawise ngetik direktori ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) bakal dieksekusi kanthi otomatis sawise ngetik direktori).

Tegese: terjemahan Cina menyang Jepang, Korea, Inggris, Inggris terjemahan menyang kabeh basa liyane. Yen sampeyan mung pengin ndhukung Cina lan Inggris, sampeyan mung bisa nulis `zh: en` .

## kode ngarep-mburi

* [kode ngarep-mburi](https://github.com/xxai-art/web)
* [Paket basa kanggo situs kanthi sakabehe](https://github.com/xxai-art/web/tree/main/i18n)
* [Paket basa kanggo modul mlebu](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Website Multilingual Documentation](https://github.com/xxai-doc)

Ing ngarep-mburi basa program punika [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , kang nambah sawetara fitur adhedhasar sintaksis coffeescript, ndeleng [./coffee_plus.md](./coffee_plus.md) .

## Internasionalisasi situs web lan dokumen

Mbangun ing 3 proyek ing ngisor iki

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Seselan yaiku `.mdt` , sampeyan bisa nggunakake sintaks sing padha karo `<+ ./coffee_plus/import.js>` kanggo ngrujuk menyang file eksternal, lan ngasilake markdown kanthi seselan `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Terjemahan Markdown ora bakal nerjemahake kode lan pranala, lan bakal nyimpen ukara terjemahan. Yen terjemahan diowahi nanging teks asli ora diowahi, eksekusi maneh ora bakal nimpa modifikasi terjemahan kasebut.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  File basa kanggo nerjemahake situs web sing digawe `yaml` .

### Pandhuan Otomasi Terjemahan Dokumen

Deleng repositori kode [xxai-art/doc](https://github.com/xxai-art/doc)

Disaranake nginstal nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dhisik, banjur `direnv allow` sawise ngetik direktori ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) bakal dieksekusi kanthi otomatis sawise ngetik direktori).

Kanggo ngindhari basis kode gedhe sing diterjemahake menyang atusan basa, aku nggawe basis kode sing kapisah kanggo saben basa lan nggawe organisasi kanggo nyimpen basis kode kasebut.

Nyetel variabel lingkungan `GITHUB_ACCESS_TOKEN` banjur mbukak [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) bakal nggawe gudang kode kanthi otomatis.

Mesthi, sampeyan uga bisa nyelehake ing basis kode.

Referensi naskah terjemahan [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Kode skrip diinterpretasikake kaya ing ngisor iki:

[bunx](https://bun.sh/docs/cli/bunx) minangka panggantos kanggo npx, sing luwih cepet. Mesthi, yen sampeyan ora duwe bun diinstal, sampeyan bisa nggunakake `npx` tinimbang.

`bunx mdt zh` nerjemahake `.mdt` ing direktori zh minangka `.md` , deleng 2 file sing disambung ing ngisor iki

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` minangka kode inti kanggo terjemahan (yen sampeyan mung nginstal `nodejs` , nanging `bun` lan `direnv` ora diinstal, sampeyan uga bisa mbukak `npx i18n` kanggo nerjemahake).

Bakal ngurai [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , konfigurasi `i18n.yml` ing dokumen iki kaya ing ngisor iki:

```
en:
zh: ja ko en
```

Tegese: terjemahan Cina menyang Jepang, Korea, Inggris, Inggris terjemahan menyang kabeh basa liyane. Yen sampeyan mung pengin ndhukung Cina lan Inggris, sampeyan mung bisa nulis `zh: en` .

Sing terakhir yaiku [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , sing ngekstrak isi antarane judhul utama lan subtitle pisanan saben basa `README.md` kanggo ngasilake entri `README.md` . Kode banget prasaja, sampeyan bisa ndeleng dhewe.

Google API digunakake kanggo terjemahan gratis. Yen sampeyan ora bisa ngakses Google, atur lan setel proxy, kayata:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Skrip terjemahan bakal ngasilake cache sing diterjemahake ing direktori `.i18n` , mangga dipriksa nganggo `git status` lan ditambahake menyang gudang kode supaya ora diterjemahake bola-bali.

Bukak `bunx i18n` saben sampeyan ngowahi terjemahan kanggo nganyari cache.

Yen teks asli lan terjemahan diowahi bebarengan, cache bakal bingung, dadi yen sampeyan pengin ngowahi, sampeyan mung bisa ngowahi siji, banjur mbukak `bunx i18n` kanggo nganyari cache.
