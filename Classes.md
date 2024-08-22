Pour créer un projet en Java qui gère une structure pour les employés, vous pouvez suivre ces spécifications :

### 1. Classe `Employe`
Cette classe représentera chaque employé avec des attributs comme `ID`, `nom`, `poste`, et `salaire`. Elle contiendra également des méthodes getter et setter pour chaque attribut.

```java
public class Employe {
    private int id;
    private String nom;
    private String poste;
    private double salaire;

    // Constructeur
    public Employe(int id, String nom, String poste, double salaire) {
        this.id = id;
        this.nom = nom;
        this.poste = poste;
        this.salaire = salaire;
    }

    // Getters
    public int getId() {
        return id;
    }

    public String getNom() {
        return nom;
    }

    public String getPoste() {
        return poste;
    }

    public double getSalaire() {
        return salaire;
    }

    // Setters
    public void setId(int id) {
        this.id = id;
    }

    public void setNom(String nom) {
        this.nom = nom;
    }

    public void setPoste(String poste) {
        this.poste = poste;
    }

    public void setSalaire(double salaire) {
        this.salaire = salaire;
    }

    @Override
    public String toString() {
        return "ID: " + id + ", Nom: " + nom + ", Poste: " + poste + ", Salaire: " + salaire;
    }
}
```

### 2. Classe `GestionEmployes`
Cette classe contiendra la logique de gestion des employés, comme l'ajout, la suppression, et l'affichage des détails des employés.

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class GestionEmployes {
    private List<Employe> listeEmployes;

    public GestionEmployes() {
        listeEmployes = new ArrayList<>();
    }

    // Ajouter un employé
    public void ajouterEmploye(Employe employe) {
        listeEmployes.add(employe);
    }

    // Supprimer un employé par ID
    public void supprimerEmploye(int id) {
        Iterator<Employe> it = listeEmployes.iterator();
        while (it.hasNext()) {
            Employe emp = it.next();
            if (emp.getId() == id) {
                it.remove();
                System.out.println("Employé avec ID " + id + " supprimé.");
                return;
            }
        }
        System.out.println("Aucun employé trouvé avec ID " + id);
    }

    // Afficher les détails de tous les employés
    public void afficherTousLesEmployes() {
        if (listeEmployes.isEmpty()) {
            System.out.println("Aucun employé dans la liste.");
        } else {
            for (Employe employe : listeEmployes) {
                System.out.println(employe);
            }
        }
    }

    // Afficher les détails d'un employé spécifique par ID
    public void afficherEmployeParId(int id) {
        for (Employe employe : listeEmployes) {
            if (employe.getId() == id) {
                System.out.println(employe);
                return;
            }
        }
        System.out.println("Aucun employé trouvé avec ID " + id);
    }
}
```

### 3. Classe `Main`
La classe `Main` est le point d'entrée du programme où vous pouvez tester les fonctionnalités.

```java
public class Main {
    public static void main(String[] args) {
        GestionEmployes gestion = new GestionEmployes();

        // Ajouter des employés
        gestion.ajouterEmploye(new Employe(1, "Alice", "Développeur", 50000));
        gestion.ajouterEmploye(new Employe(2, "Bob", "Designer", 45000));
        gestion.ajouterEmploye(new Employe(3, "Charlie", "Manager", 60000));

        // Afficher tous les employés
        System.out.println("Liste des employés:");
        gestion.afficherTousLesEmployes();

        // Afficher un employé spécifique
        System.out.println("\nDétails de l'employé avec ID 2:");
        gestion.afficherEmployeParId(2);

        // Supprimer un employé
        gestion.supprimerEmploye(1);

        // Afficher tous les employés après suppression
        System.out.println("\nListe des employés après suppression:");
        gestion.afficherTousLesEmployes();
    }
}
```

### Explication :
- **Classe `Employe`**: Gère les informations de base d'un employé.
- **Classe `GestionEmployes`**: Contient une liste d'employés et fournit des méthodes pour ajouter, supprimer et afficher les employés.
- **Classe `Main`**: Permet de tester les fonctionnalités définies.

En exécutant la classe `Main`, vous verrez comment les employés sont ajoutés, supprimés, et comment leurs informations sont affichées.

Vous pouvez adapter et améliorer ce code en fonction des besoins spécifiques de votre projet.
