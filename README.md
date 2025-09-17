site-dockerfile-git/
├─ index.html
└─ Dockerfile


#Étapes locales (Git + GitHub)

# 1) Créer le dossier projet
mkdir C:\openshift\site-dockerfile-git
cd C:\openshift\site-dockerfile-git

# 2) Initialiser le dépôt Git
git init

# 3) Créer index.html (ou copiez le contenu ci-dessus)
# 4) Créer Dockerfile (ou copiez le contenu ci-dessus)

# 5) Ajouter le remote GitHub et pousser
git remote add origin https://github.com/<user>/site-dockerfile-git.git...........mon user :Ibramove
git add .
git commit -m "Ajout Dockerfile et index.html"
git branch -M main
git push -u origin main




#Déploiement sur OpenShift
# 1) Créer l’app directement depuis le repo GitHub
oc new-app https://github.com/<user>/site-dockerfile-git.git --name=site-github-dockerfile

# 2) Vérifier les ressources
oc get pods
oc get svc

# 3) Exposer une route publique
oc expose service site-github-dockerfile

# 4) Récupérer l’URL et tester
oc get route
# Exemple de test (remplacez <URL>):
curl http://<URL>

<img width="3042" height="618" alt="image" src="https://github.com/user-attachments/assets/bde36293-f2ae-4b1e-86a2-bcce4dd23eb3" />

