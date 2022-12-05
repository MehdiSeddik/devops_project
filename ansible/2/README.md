# Création du mot de passe + Hash

Pour la partie "Création d'un utilisateur, vous pouvez utiliser les commandes suivantes pour générer le hash SHA512 :

```bash
pass=`pwgen --capitalize --numerals --secure --symbols 12 1`

echo $pass | mkpasswd --stdin --method=sha-512; echo $pass
```
