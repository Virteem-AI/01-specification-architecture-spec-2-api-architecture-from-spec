# Script vidéo - SPEC-2

## Alignement avec `New_training_content.md`

"Il n'y a pas de section `Script —` dédiée à cet exercice. Ce script est aligné sur l'exercice Hands On `Designing the API Architecture from the Spec` et sur les parties du module qui expliquent Plan Mode, les ADR et l'architecture comme contrat."

## Concept couvert

"Ce Hands On couvre la phase Design de l'AIDLC. Une specification décrit ce que le système doit faire ; le design explique comment le système va être organisé pour le faire correctement."

"Le concept important ici est le rôle de l'architecture comme second contrat donné à l'agent. Sans design explicite, l'IA peut produire du code qui fonctionne localement mais qui ne respecte pas les responsabilités ou les conventions du système."

"Dans un contexte réel, c'est à ce moment que l'on évite les mauvaises surprises : mauvaise séparation des responsabilités, validation dispersée, erreurs incohérentes, ou choix techniques difficiles à maintenir. Le design sert à aligner l'humain, l'équipe et l'agent avant l'écriture du code."

"L'autre concept important est l'ADR, Architecture Decision Record. Un ADR ne décrit pas tout le système ; il capture une décision et son raisonnement. Pour un agent IA, c'est extrêmement utile, car cela transforme une préférence implicite en contrainte explicite."

## Mise en situation

"Nous avons déjà une specification fonctionnelle de l'API TaskFlow. Maintenant, nous devons la transformer en design technique : fichiers, responsabilités, stratégie de validation, gestion des erreurs et flux de données."

"À l'écran, ouvrez `spec-reference.md` et montrez que le document décrit les endpoints, le modèle de données et les erreurs. Expliquez que ce document dit quoi faire, mais pas encore comment organiser l'implémentation."

"Posez les questions de design : faut-il un seul fichier ou plusieurs modules ? où placer la validation ? comment garder un format d'erreur cohérent ? comment documenter le flux de création d'une tâche ?"

## Démonstration du début

"J'ouvre `spec-reference.md`, puis je demande à Copilot en Plan Mode de proposer un design sans générer de code. Je précise : module structure, route definitions, validation approach, error handling strategy."

"Ensuite, je demande un ADR sur le choix d'une application Flask mono-fichier avec stockage en mémoire, puis un diagramme Mermaid pour visualiser le flux `POST /tasks`."

"Pendant la démonstration, insistez sur le fait que Plan Mode est utilisé pour réfléchir, pas pour modifier les fichiers tout de suite. On veut obtenir un plan lisible, puis le valider."

"Montrez comment Copilot peut proposer plusieurs options. Par exemple, une architecture mono-fichier est pertinente pour un exercice court, mais une architecture en modules serait préférable pour une application plus grande. Le choix doit être expliqué, pas seulement appliqué."

"Quand vous demandez l'ADR, montrez les quatre parties attendues : context, decision, alternatives considered, consequences. Expliquez que les conséquences négatives sont aussi importantes que les positives."

"Pour le diagramme Mermaid, montrez que le flux rend visible la séquence client, route Flask, validation, stockage et réponse. Cela aide les participants à penser en termes de comportement, pas seulement de fichiers."

## Consignes pour l'exercice

"Votre livrable est `design.md`. Il doit permettre à quelqu'un d'implémenter l'API sans poser de nouvelles questions de structure."

"Le document doit contenir une structure de fichiers, les responsabilités, les routes, les règles de validation, la stratégie d'erreur, un ADR et un diagramme."

"Demandez aussi à Copilot : 'What are the limitations of this design for production ?' Cette question est importante, car elle apprend à ne pas confondre un design pédagogique avec un design production-ready."

## Points d'attention à montrer à l'écran

"Montrez la différence entre specification et design. La specification dit : POST /tasks crée une tâche. Le design dit : quelle route traite la requête, quelle fonction valide l'entrée, où la tâche est stockée, quel format de réponse est retourné."

"Montrez une décision discutable et expliquez-la. Par exemple : 'single-file Flask app'. C'est volontairement simple pour le Hands On, mais il faut documenter que ce choix ne serait pas forcément adapté à une application de production."

## Conclusion

"Le design est une étape de contrôle avant l'implémentation. Avec un agent IA, cette étape devient encore plus importante, car elle évite de laisser l'agent inventer seul l'organisation du système."

"Le réflexe à retenir : avant de demander du code multi-fichiers, demandez un design, validez-le, puis seulement ensuite passez à l'implémentation."
