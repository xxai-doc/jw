<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Bagéyan saka kode situs web minangka sumber terbuka, welcome kanggo mbantu ngoptimalake terjemahan.

## kode ngarep-mburi

* [kode ngarep-mburi](https://github.com/xxai-art/web)
* [Paket basa kanggo situs kanthi sakabehe](https://github.com/xxai-art/web/tree/main/i18n)
* [Paket basa kanggo modul mlebu](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Website Multilingual Documentation](https://github.com/xxai-doc)

Ing ngarep-mburi basa program punika [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , kang nambah sawetara fitur adhedhasar sintaksis coffeescript, ndeleng [./coffee_plus.md](./coffee_plus.md) .

## Internasionalisasi situs web lan dokumen

Mbangun ing 3 proyek ing ngisor iki

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

Cithakan markdown, kanthi seselan `.mdt` , bisa ngrujuk menyang file eksternal kanthi sintaks sing padha karo `<+ ./coffee_plus/import.js>` .

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Terjemahan Markdown ora bakal nerjemahake kode lan pranala, lan bakal nyimpen ukara terjemahan. Yen terjemahan diowahi nanging teks asli ora diowahi, eksekusi maneh ora bakal nimpa modifikasi terjemahan kasebut.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

File basa kanggo nerjemahake situs web sing digawe `yaml` .
