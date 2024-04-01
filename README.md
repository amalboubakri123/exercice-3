#include <bits/stdc++.h>
using namespace std;

class Vehicule {
protected :
string immatriculation ;
float poids_a_vide ;
int vitesse_max;
 public :
Vehicule() {}
Vehicule(string c) {immatriculation=c;}
virtual ~Vehicule(){}
float consommation (int v, int p) const{return ((v)/10 + (p)) ;}
virtual void affichage () const { cout<<" immatriculation"<<immatriculation<<endl ;}
virtual int calcul_vitesse_maximale ()=0 ;
 } ;
class Petit_bus : public Vehicule {
 public:
Petit_bus(){poids_a_vide=4;
vitesse_max=150;}
~Petit_bus (){}
void affichage () const { Vehicule :: affichage() ;
cout<< " poids à vide"<<poids_a_vide<< " vitesse_max "<<vitesse_max<<endl;}
int calcul_vitesse_maximale (){ return vitesse_max ;}
 };
class Camion_citerne : public Vehicule{
int charge ;
int charge_max ;
 public:
Camion_citerne (){poids_a_vide=3;
charge_max =10;}
void set_charge(int c){if(c<charge_max)charge=c ;}
int get_charge() const {return charge ;}
void affichage () const{ Vehicule :: affichage() ;
cout<< "poids à vide "<<poids_a_vide<< "charge "<<charge<< "charge_max "<<charge_max<<endl;}
int calcul_vitesse_maximale (){ if (charge==0) vitesse_max= 130 ;
else if (charge <=1) vitesse_max=110 ;
else if (charge <=4) vitesse_max= 90 ;
else if (charge >4) vitesse_max=80 ;
return vitesse_max ;}
} ; 
class Camion_bache : public Vehicule{
int charge ;
int charge_max ;
public:
Camion_bache(){poids_a_vide=4;
charge_max =20;}
void set_charge(int c){if(c<charge_max)charge=c ;}
int get_charge() const {return charge ;}
void affichage () const{ Vehicule :: affichage() ;
cout<< "poids à vide "<<poids_a_vide<< "charge "<<charge<< "charge_max"<<charge_max<<endl;}
int calcul_vitesse_maximale (){ if (charge==0) vitesse_max= 130 ;
else if (charge <=3) vitesse_max=110 ;
else if (charge <=7) vitesse_max= 90 ;
else vitesse_max=80 ;
return vitesse_max ;}
} ;
