# Revisión ortográfica

¡Corrija sus errores ortográficos!

::: tip Info
QOwnNotes tiene una función incorporada **Dictionary Manager** (in the *Edit* menu) que puede utilizar para descargar diccionarios o eliminarlos (si le falta su idioma, consulte a continuación cómo solicitar la adición de un diccionario). Si desea descargar los diccionarios manualmente, puede seguir las instrucciones a continuación.
:::

- En **Linux** puede instalar los diccionarios Hunspell para su idioma usando el administrador de paquetes de su distribución
    - Si necesita agregar archivos de idioma adicionales, puede hacerlo en `~/.local/share/hunspell` or `/usr/share/hunspell`.
    - Si está utilizando el paquete Snap de QOwnNotes, también puede usar `~/hunspell` para archivos de idioma, ya que Snap no puede acceder a `~/.local`

- En **Windows **, debe copiar los diccionarios Hunspell para su idioma en una carpeta `dicts` en la carpeta de su aplicación QOwnNotes o en `C:\Users\[username]\dicts`
    - Puede descargar diccionarios de [diccionarios de LibreOffice](https://github.com/LibreOffice/dictionaries)
    - En **macOS** debe copiar los diccionarios Hunspell para su idioma a `/Library/Spelling` o `~/Library/Spelling`. Si el directorio no existe, debe crearlo.

Los diccionarios se pueden descargar desde [diccionarios QOwnNotes](https://github.com/qownnotes/dictionaries). Utilice la tabla al final de este documento para encontrar su idioma y su código de idioma respectivo.

Si el diccionario para su idioma no está en el **Administrador de diccionarios** o en el enlace mencionado anteriormente, búsquelo en Internet o cree un problema. Nos aseguraremos de incluirlo en la próxima versión de QOwnNotes si se encuentra el diccionario.

::: Información de la sugerencia Si no puede encontrar su idioma en esta tabla, desafortunadamente no existe un diccionario para él en los archivos de LibreOffice. Si desea crear un diccionario, vaya a [Desarrollo de diccionarios de Documentfoundation.org](https://wiki.documentfoundation.org/Development/Dictionaries)
:::

| Sr | Código del lenguaje | Lenguaje                   |
| -- | ------------------- | -------------------------- |
| 1  | af_ZA               | Afrikáans (Sudáfrica)      |
| 2  | an_ES               | Aragonés                   |
| 3  | ar                  | Árabe                      |
| 4  | be_BY               | Bielorruso                 |
| 5  | bg_BG               | Búlgaro                    |
| 6  | bn_BD               | Bengalí                    |
| 7  | bo                  | Tibetano                   |
| 8  | br_FR               | Bretón (Francia)           |
| 9  | bs_BA               | Bosnio                     |
| 10 | ca                  | Catalán                    |
| 11 | cs_CZ               | Checo                      |
| 12 | da_DK               | Danés                      |
| 13 | de                  | Alemán                     |
| 14 | el_GR               | Griego                     |
| 15 | en                  | Inglés                     |
| 16 | es                  | Español                    |
| 17 | et_EE               | Estonio                    |
| 18 | gd_GB               | Gaélico                    |
| 19 | gl                  | Gallego                    |
| 20 | gu_IN               | Guyaratí                   |
| 21 | gug                 | Guaraní                    |
| 22 | he_IL               | Hebreo                     |
| 23 | hi_IN               | Hindi                      |
| 24 | hr_HR               | Croata                     |
| 25 | id                  | Indonesio                  |
| 26 | it_IT               | Italiano                   |
| 27 | kmr_Latn            | Kurdo (Turquía)            |
| 28 | lo_LA               | Laosiano                   |
| 29 | lt_LT               | Lituano                    |
| 30 | lv_LV               | Letón                      |
| 31 | ne_NP               | Nepalés                    |
| 32 | nl_NL               | Holandés                   |
| 33 | no                  | Noruego                    |
| 34 | oc_FR               | Occitano                   |
| 35 | pl_PL               | Polaco                     |
| 36 | pt_BR               | Portugués brasileño        |
| 37 | pt_PT               | Portugués                  |
| 38 | ro                  | Rumano                     |
| 39 | ru_RU               | Ruso                       |
| 40 | si_LK               | Sinhalese                  |
| 41 | sk_SK               | Eslovaco                   |
| 42 | sl_Sl               | Esloveno                   |
| 43 | sq_AL               | Albanés                    |
| 44 | sr                  | Serbio                     |
| 45 | sv_SE               | Sueco                      |
| 46 | sw_TZ               | Suajili                    |
| 47 | te_IN               | Télugu                     |
| 48 | th_TH               | Tailandés                  |
| 49 | tr_TR               | Turco                      |
| 51 | uk_UA               | Ucraniano                  |
| 52 | vi                  | Vietnamita                 |
| 53 | zu_ZA               | Zulu(spell dict not avail) |

::: tip
Credits [Sonnet](https://github.com/KDE/sonnet) con [Hunspell](https://hunspell.github.io/) se utiliza para corregir la ortografía
:::
