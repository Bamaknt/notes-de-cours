# Céer le référentiel et cloner en sélectionnant l'option SSH
1. Le prompt de Gitbash nous affichera ceci:
$ git clone git@github.com:accountname/repositoryname.git
Cloning into 'repositoryname'...
The authenticity of host 'github.com (140.82.121.4)' can't be established.
ED25519 key fingerprint is SHA123:+Alphanumérique/Alphanumérique.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
2. Voyons si nous avons une clé SSH en saisissant:
$ ls -la ~/.ssh
3. Ensuite on va activer l'agent SSH en saisissant:
$ eval "$(ssh-agent -s)"
On aura: Agent pid 123
4. On va alors générer notre clé SSH en saisissant:
$ ssh-keygen
Gitbash affichera:
Generating public/private ed25519 key pair.
Enter file in which to save the key (/c/Users/username/.ssh/id_ed25519):
Enter passphrase for "/c/Users/username/.ssh/id_ed25519" (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/username/.ssh/id_ed25519
Your public key has been saved in /c/Users/username/.ssh/id_ed25519.pub
The key fingerprint is:
SHA123:Alphanumérique/Alphanumérique username@Hostname
The key's randomart image is:
5. Enfin on va afficher notre clé SSH en saisissant:
$ cat ~/.ssh/id_ed25519.pub
Gitbash affichera:
ssh-ed25519 Alphanumérique+Alphanumérique username@BamaZHostname
6. Nous allons sur notre espace GitHub 
- Cliquez sur notre photo de profil
- Cliquer sur settings
- Cliquer sur SSH and GPG Keys
- Allez sur la rubrique Add new SSH Key
- Renseigner le champ Title du nom de votre clé SSH
- Aller copier la ligne en bas du cat... et venir la coller dans le champ Key en dessous de Title
- Cliquer sur le bouton Add SSH key en vert
7. Repartir cliquer sur le bouton Code copier le lien généré SSH
8. Retourner sur Gitbash et saisir au prompt:
$ git clone git@github.com:accountname/repositoryname.git
9. Gitbash affichera:
$ git clone git@github.com:accountname/repositoryname.git
Cloning into 'repositoryname'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (4/4), done.





