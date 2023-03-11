## Particularités
- RustLang introduit le concept de macro, ce qui permet la métaprogrammation. Au lieu de faire un appel de fonctions, les macros insèrent du code source lors de la compilation. Les macros se terminent par un ! (ex.: println!)

## CLI Rust
- rustc <fichier.rs> permet de compiler un fichier

## Normes
### Style
- Maximum 99 caractères par ligne
- Indentation: 4 espaces (pas un tab)
- Pas de d'espaces en fin de ligne ou de fichier

### Nommage
- snake_case: crates, modules, functions, methodes, variables locales
- CamelCase: types, traits, enum variants, type parameter (court)
- SCREAMING_SNAKE_CASE: variables statiques ou constantes

### Commentaires
- Commentaire sur une ligne: //
- Commentaire variables ou mutlilignes: /* */ (À éviter sauf pour commenter en plein milieu d'une ligne)
- Commentaire pour la documentation: ///
- Commentaire général pour une classe: //!

## Affichage console
Provient d'une série de macro dans std::fmt
- format!: Texte formatté vers string
- print!: Affiche du texte formatté dans la console (io::stdout)
- println!: print! avec lignes
- eprint!: print! pour les erreurs (io::stderr)
- eprintln!: eprintln! avec nouvelle ligne

### Formattage
- {}: standard
- {:b}: Binaire 
- {:o}: Octal 
- {:x}: Hexadecimal minuscule 
- {:X}: Hexadecimal majuscule 
- {NOM}: Pour utiliser des clés au lieu de l'index 
- {:?}: Standard (={}) 
- #[derive(Debug)]: Pour debug (avant ligne, puis {:?}
- {:#?} : Pretty print
- [Display](https://doc.rust-lang.org/rust-by-example/hello/print/print_display.html) doit être implémenté manuellement


## Types
