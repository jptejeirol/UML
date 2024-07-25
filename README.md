# UML
Mermaid Diagrams

classDiagram
    class Diseno {
        -base Integer
        -altura Integer
        -profundidad Integer
        +getBase() Integer
        +getAltura() Integer
        +getProfundidad() Integer
        +setBase(Integer) void
        +setAltura(Integer) void
        +setProfundidad(Integer) void
        +toString() String
    }
    
    class FirebasePushObject {
        -firebaseDatabase FirebaseDatabase
        +initFirebase() void
        +saveItem(Item) void
        +saveDiseno(Diseno) void
        +saveUsuario(Usuario) void
        +getItem(String, ValueEventListener) void
        +updateItem(String, Item) void
        +deleteUser(String) void
    }
    
    class FirebaseSaveObject {
        -firebaseDatabase FirebaseDatabase
        -initFirebase() void
        +save(Item) void
    }
    
    class Item {
        -base Integer
        -altura Integer
        -profundidad Integer
        +getBase() Integer
        +getAltura() Integer
        +getProfundidad() Integer
        +setBase(Integer) void
        +setAltura(Integer) void
        +setProfundidad(Integer) void
        +toString() String
    }
    
    class Menu {
        +main(String[]) void
    }
    
    class Usuario {
        -username String
        -password String
        -email String
        -name String
        +getUsername() String
        +setUsername(String) void
        +getPassword() String
        +setPassword(String) void
        +getEmail() String
        +setEmail(String) void
        +getName() String
        +setName(String) void
        +toString() String
    }
    
    Menu "1" ..> "1" FirebasePushObject
    Menu "1" *-- "0..*" Diseno
    Menu "1" *-- "0..*" Item
    Menu "1" *-- "0..*" Usuario
    FirebasePushObject "1" ..> "0..*" Item
    FirebasePushObject "1" ..> "0..*" Diseno
    FirebasePushObject "1" ..> "0..*" Usuario
    FirebaseSaveObject "1" ..> "0..*" Item
