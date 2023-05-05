# Mon_Pendule-python
import random
MotDeviner=["","","","","","",""]
MotsAdeviner = ['Couleur', 'Bonjour', 'Bonsoir', 'Ecarlat']
NombreEssaie=0
TableauIntermediere = [0, 0, 0, 0, 0, 0, 0]
IndiceMotChoisi=random.randint(0,len(MotsAdeviner))
MotChoisi=MotsAdeviner[IndiceMotChoisi]
while (NombreEssaie <=2):
    print("Bienvenu dans le jeu de pendu ")
    print("Entrez le mot a deviner")
    MotSaisie = input()
    if(MotSaisie != MotChoisi):
        NombreEssaie = NombreEssaie + 1
        for i in range (len(MotChoisi)):
            if (MotChoisi[i]==MotSaisie[i]):
                print(f"bravo lettre {MotChoisi[i]} presente dans le mot")
                TableauIntermediere[i]=1
                print(MotChoisi[i])
            else:
                if TableauIntermediere[i]!=1:
                    TableauIntermediere[i]=0
            MotDeviner[i] = MotChoisi[i] if TableauIntermediere[i] == 1 else "*"
            print("ESSAIE RESTANT:",3-NombreEssaie)
            print("Votre situation actuel est :", MotDeviner)
            print(MotsAdeviner[IndiceMotChoisi])
    else:
        print("Felicitation a vous ")
        print(MotsAdeviner)
        break
