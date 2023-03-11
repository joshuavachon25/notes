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


## Variables (typage)
### Primitives
#### Simples
- INT signés: i8, i16,  i32, i64, i128, isize
- INT non signés: u8, u16, u32, u64, u128, usize
- FLOAT: f32, f64
- CHAR: char 
- BOOL: bool
- Unit type: () (valeur possible = ())
#### Composées
- Array: [] Collection d'objet du même type
- Tuple: () Collections de valeurs de types différents

#### Math
- Literals: VALEURTYPE ex.: 1u32, 123i32...
- Hexa: 0x
- Octal: 0o
- Binaire: 0b
- Notation scientifique: ex:. 1e6 (type = f64)
- Lisibilité: Mettre des underscores pour chaque paquet de trois

#### Array
##### Initialisation
let ys: [type; nb element] = [Valeur par défaut; nb element];
ou
let xs: [type: nb element] = [v1,v2,v3,v4,vn...]

##### Méthodes
.len() Nombre d'éléments
[1 .. 3] Slice 1 à 3

### Types personnalisées
#### Structures
- Trois types: Tuple, C Structs, Unit Struct

## Gestion de la mémoire
- mem::size_of_value() permet de calculer l'espace mémoire pris par une variable
