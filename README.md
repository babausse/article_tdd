# Ce que la Science nous apprend du TDD

En tant que développeur, je pense que les tests automatisés et le TDD (Test-Driven Development, ou en français “développement piloté par les tests”) sont des outils essentiels à la production d’applications de qualité. Je pense également qu’ils contribuent à réduire le stress des développeurs, augmentent la confiance dans le code produit, permettent des livraisons plus fiables et plus régulières ; ils seraient en somme une sorte de graal du développement logiciel !

Cette connaissance intuitive, éprouvée pendant mes expériences dans différentes entreprises et confirmée par d’autres témoignages de développeurs, n’est néanmoins pas suffisante et ne saurait être une base solide pour décider d’appliquer ou non ces outils. Je me suis donc fixé pour but d’examiner la littérature scientifique à propos du TDD pour nuancer ou appuyer mes idées reçues sur le sujet avec des données fiables et rigoureuses. Pour cela, les questions que nous nous poserons sont :

*	A quelles conclusions arrive la littérature scientifique sur le TDD ?
* Que pouvons-nous en tirer pour nos propres pratiques de développement ?

## Avertissements

Le présent article n’a pas l’intention d’être une revue systématique de tous les travaux scientifiques menés au sujet du TDD et de son efficacité. Il s’agit d’une compilation de sources scientifiques revues par les pairs, publiées de 2003 à aujourd’hui, desquelles je me propose de tirer des conclusions et des actions à envisager pour améliorer l’adoption du TDD et ses bienfaits.

## Méthodologie

La recherche bibliographique que j’ai menée se décompose en deux temps :
1.	Récolte de sources secondaires (méta-études, revues systématiques) afin d’avoir accès à des conclusions agrégées et aux sources primaires.
2.	Récolte de sources primaires citées par les sources secondaires et d’autres sources primaires, afin de s’assurer que leurs conclusions n’ont pas été déformées.

## Définitions et problématique

La définition du TDD est importante, les variations entre les définitions étant un des critères montrés du doigt comme empêchant le consensus sur la question de ses bienfaits (Ghaffari et al., 2020, p. 9).

Le TDD est une méthodologie qui, si elle existe en réalité depuis les années 60, avec par exemple le projet Mercury de la NASA (Larman & Basili, 2003, p. 47), a été redécouverte en bonne partie à l’orée des années 2000 avec l’avènement des méthodologies agiles, principalement Extrem Programming (XP).

Il s’agit d’une méthodologie promouvant l’utilisation de cycles de développements très courts répondant à la séquence suivante :

*	écriture et échec d’un test unitaire
*	écriture du code minimum d’implémentation de la fonctionnalité
*	passage du test au vert
*	refactoring tout en repassant les tests et en les gardant au vert

D’autres versions de cette méthodologie ont également émergé, principalement l’ITLD (Iterative Test-Last Development) qui promeut d’écrire les tests après le code, mais qui reste techniquement un développement conduit par les tests. Malgré cela, nous considérerons que la dénomination “TDD” correspond ici à test-first, puisque dans beaucoup d’études il est comparé au “test-last” (Fucci et al., 2017).

## Que nous disent-elles ?

### Les retours de l'industrie

Un des types de publications fortement représenté est l’étude de cas rétrospective : on y évalue a posteriori l’impact de l’introduction du TDD au sein d’un projet, d’une équipe, ou d’une entreprise (Bhat & Nagappan, 2006 ; Maximilien & Williams, 2003 ; Trumler & Paulisch, 2016). Dans l’ensemble les retours d’expérience sont bons : qualité en augmentation, moins de defects, livraisons faites à temps.

__*L’industrie a de bons retours sur le TDD, en particulier sur la qualité des livrables.*__

### Couverture de tests

Le cœur méthodologique du TDD consiste à écrire les tests avec le code qu’ils valident. En stimulant cette augmentation incrémentale du nombre de tests unitaires, le TDD incite à en écrire plus (Fucci et al., 2018), et à augmenter la proportion de code couvert par les tests (Papis et al., 2020). C’est cette incitation à écrire des tests qui semble le principal facteur dans les augmentations constatées de qualité, et la réduction du nombre de bugs.

__*Le TDD incite à écrire plus de tests et à couvrir plus de code par les tests.*__

### Qualité de code

La qualité externe d’une application est sa complétude fonctionnelle, et la quantité de defects rencontrés par ses utilisateurs. Pour cette métrique, le TDD est bénéfique dans la plupart des cas (Rafique & Misic, 2013 ; Bissi et al., 2016) et le nombre de defects peut être significativement réduit.

__*Les applications répondent donc mieux aux besoins des utilisateurs, et produisent moins de bugs à l’utilisation.*__

La qualité interne concerne la complexité du code en lui-même, la capacité à le lire, le maintenir et le comprendre. Les résultats de cette métrique sont débattus car dans la plupart des cas les développeurs négligent l’étape de refactoring et produisent le code minimal pour passer les tests au vert, livrant du code fonctionnel mais de moindre qualité interne (Romano et al., 2016, p. 8 ; Scanniello et al., 2016, p. 1426). Ce manque de suivi de la méthodologie allié à des itérations très courtes pourrait défavoriser l’implémentation plus longue d’architectures complexes et difficiles à décomposer en itérations.

__*Le TDD ne permet pas d’augmenter la qualité interne des applications, mais cela est en grande partie dû à sa mauvaise application.*__

### Vélocité de développement

Sur le court terme le constat est clair : le TDD prend du temps à se mettre en place au début du développement d’une application, et diminue d’autant la vélocité de votre équipe qui pourra se sentir “ralentie” par ce cadre méthodologique.

Sur le long terme cependant, si la perte de vélocité reste réelle pour chaque tâche prise individuellement, il reste important de la mitiger : le TDD réduit drastiquement la quantité de bugs introduits dans les applications et le temps que cela fait gagner pourrait compenser la perte initiale de vélocité.

__*La vélocité est négativement impactée par le TDD pour la réalisation d’une tâche, mais permet de regagner une partie de ce temps sur le long terme par la baisse du nombre d’anomalies détectées par les utilisateurs.*__

### Satisfaction des développeurs

Lorsque les études se penchent sur la satisfaction des développeurs et la confiance qu’ils ont dans le code qu’ils ont développé, le constat est clair : le TDD est apprécié par les développeurs (George & Williams, 2004, p. 342) qui sont beaucoup plus confiants à la fois dans la complétude, dans l’exactitude, et dans la qualité du code produit (Choma et al., 2018, p. 83). Cette satisfaction entraîne mécaniquement une baisse du stress professionnel et une amélioration des conditions de travail des développeurs.

Malgré cela attention, les développeurs qui se mettent au TDD ressentent en général un fort coût d’entrée qui peut sembler dissuasif de prime abord (Unkelos-Shpigel et Hadar, 2018).

__*La phase initiale d’apprentissage surmontée, les développeurs apprécient le TDD et sont plus confiants dans leur code grâce à lui.*__

### Tester avant ou après ?

On arrive à la conclusion la plus contre-intuitive : tester avant ou après l’écriture du code semble ne pas avoir de conséquences statistiquement parlant ; et même, écrire les tests après le code permettrait une plus grande qualité externe (Tosun et al., 2020, p. 12). Certaines publications sont plus contrastées, ou ne trouvent pas de différences entre significatives entre TDD et ITLD pour la qualité (Erdogmus et al., 2005, p. 237)

__*Tester avant ou après l’écriture du code ne semble pas être un facteur déterminant.*__

### Amélioration de l’apprentissage

Sur ce point la science est relativement unanime : le TDD permet un apprentissage plus efficace des concepts de développement en passant d’une logique d’essais et erreurs à une logique de réflexion dans l’action (Edwards, 2004). Au lieu de simplement produire un résultat et se conformer aux tests de l’évaluateur de leurs programmes, les étudiants imaginent comment doit fonctionner leur programme en étant forcés de rédiger des tests avant le code. Cette étape d’abstraction et de conception permet une compréhension plus profonde des fonctionnalités liées à leur code (Bhadauria et al., 2020).

__*Le TDD permet un apprentissage plus facile de la conception logicielle.*__

## D’autres facteurs entrent-ils en jeu ?

Le seul fait de tester avant le code ne semble pas être le facteur qui explique le mieux toutes les conclusions. Un des facteurs notables est par exemple le découpage des tâches en amont : plus les tâches sont découpées finement et régulièrement, plus le TDD semble être efficace, en particulier auprès des développeurs novices (Karac et al., 2020, p. 11 ; Tosun et al., 2020, p. 17).

D’autres facteurs peuvent être éliminés : l’environnement de développement (Santos et al., 2020, p. 31) ou l’ordre des différentes tâches par exemple.

## Conclusion

La littérature sur le TDD ne permet pas d’obtenir un consensus clair sur chacun de ses aspects, mais sa lecture attentive peut permettre de dégager à la fois les avantages qu’il présente et les facteurs qui favorisent son adoption et ses bienfaits.

Les évangélistes du TDD devraient continuer à promouvoir cette méthodologie dans les équipes qu’ils intègrent, mais devraient peut-être revoir la priorité des éléments constitutifs du TDD : soyez toujours intransigeants sur l’écriture de tests, mais plus souple sur l’ordre des tests et de la rédaction de code dans un premier temps. Simplifiez l’adoption du refactoring en l’intégrant au dimensionnement de vos sprints (dans le cas où vous utilisez une méthodologie agile type SCRUM). Soyez également transparents sur les inconvénients, en particulier la perte de productivité immédiate.

Les développeurs junior, ou celles et ceux n’ayant pas encore adopté le TDD, pourront également y trouver leur compte : appliquez le TDD quand vous en avez l’occasion et que les conditions sont réunies, et essayez de vous y tenir pendant une période prolongée afin de passer le cap de la difficulté initiale pour avoir accès aux avantages à long terme.

Un mot enfin à vous qui dirigez ou organisez les développements d’une équipe : le TDD a un fort coût d’accès qui pourrait sembler rédhibitoire, mais peut apporter de nombreux avantages à votre projet. Ces avantages sont : livraisons plus régulières, moins de retour de bugs (et donc augmentation de la confiance des clients), moins de stress pour les développeurs. Malgré cela vous avez vous aussi votre rôle à jouer : découpez les tâches au mieux en amont, et assurez-vous de leur compréhension par toute l’équipe pour faciliter l’adoption et le succès du TDD.

## Sources

Bhadauria, V., Mahapatra, R. K., & Nerur, S. (2020). Performance Outcomes of Test-Driven Development : An Experimental Investigation. Journal of the Association for Information Systems, 21, 1045‑1071. [doi](https://doi.org/10.17705/1jais.00628)

Bhat, T., & Nagappan, N. (2006). Evaluating the efficacy of test-driven development. Proceedings of the 2006 ACM/IEEE international symposium on International symposium on empirical software engineering - ISESE ’06, 356‑363. [doi](https://doi.org/10.1145/1159733.1159787)

Bissi, W., Serra Seca Neto, A. G., & Emer, M. C. F. P. (2016). The effects of test driven development on internal quality, external quality and productivity : A systematic review. Information and Software Technology, 74, 45‑54. [doi](https://doi.org/10.1016/j.infsof.2016.02.004)

Choma, J., Guerra, E. M., & da Silva, T. S. (2018). Developers’ Initial Perceptions on TDD Practice : A Thematic Analysis with Distinct Domains and Languages. Lecture Notes in Business Information Processing, 68‑85. [doi](https://doi.org/10.1007/978-3-319-91602-6_5)

Edwards, S. H. (2004). Using software testing to move students from trial-and-error to reflection-in-action. Proceedings of the 35th SIGCSE technical symposium on Computer science education - SIGCSE ’04, 26‑30. [doi](https://doi.org/10.1145/971300.971312)

Erdogmus, H., Morisio, M., & Torchiano, M. (2005). On the effectiveness of the test-first approach to programming. IEEE Transactions on Software Engineering, 31(3), 226‑237. [doi](https://doi.org/10.1109/tse.2005.37)

Fucci, D., Erdogmus, H., Turhan, B., Oivo, M., & Juristo, N. (2017). A Dissection of the Test-Driven Development Process : Does It Really Matter to Test-First or to Test-Last ? IEEE Transactions on Software Engineering, 43(7), 597‑614. [doi](https://doi.org/10.1109/tse.2016.2616877)

Fucci, D., Turhan, B., Juristo, N., Dieste, O., Tosun-Misirli, A., & Oivo, M. (2015). Towards an operationalization of test-driven development skills : An industrial empirical study. Information and Software Technology, 68, 82‑97. [doi](https://doi.org/10.1016/j.infsof.2015.08.004)

George, B., & Williams, L. (2004). A structured experiment of test-driven development. Information and Software Technology, 46(5), 337‑342. [doi](https://doi.org/10.1016/j.infsof.2003.09.011)

Ghafari, M., Gross, T., Fucci, D., & Felderer, M. (2020). Why Research on Test-Driven Development is Inconclusive ? Proceedings of the 14th ACM / IEEE International Symposium on Empirical Software Engineering and Measurement (ESEM), 1‑10. [doi](https://doi.org/10.1145/3382494.3410687)

Karac, E. I., Turhan, B., & Juristo, N. (2020). A Controlled Experiment with Novice Developers on the Impact of Task Description Granularity on Software Quality in Test-Driven Development. IEEE Transactions on Software Engineering, 1. [doi](https://doi.org/10.1109/tse.2019.2920377)

Larman, C., & Basili, V. R. (2003). Iterative and incremental developments. a brief history. Computer, 36(6), 47‑56. [doi](https://doi.org/10.1109/mc.2003.1204375)  
Maximilien, E. M., & Williams, L. (2003). Assessing test-driven development at IBM. 25th International Conference on Software Engineering, 2003. Proceedings., 1‑6. [doi](https://doi.org/10.1109/icse.2003.1201238)

Papis, B. K., Grochowski, K., Subzda, K., & Sijko, K. (2020). Experimental evaluation of test-driven development with interns working on a real industrial project. IEEE Transactions on Software Engineering, 1. [doi](https://doi.org/10.1109/tse.2020.3027522)

Rafique, Y., & Misic, V. B. (2013). The Effects of Test-Driven Development on External Quality and Productivity : A Meta-Analysis. IEEE Transactions on Software Engineering, 39(6), 835‑856. [doi](https://doi.org/10.1109/tse.2012.28)

Romano, S., Fucci, D., Scanniello, G., Turhan, B., & Juristo, N. (2016). Results from a Ethnographically-Informed study in the context of test driven development. ACM International Conference Proceeding Series, 1‑10. [doi](https://doi.org/10.1145/2915970.2915996)

Santos, Adrian & Vegas, Sira & Dieste Tubío, Óscar & Uyaguari, Fernando & Tosun, Aysee & Fucci, Davide & Turhan, Burak & Scanniello, Giuseppe & Romano, Simone & Karac, Itir & Kuhrmann, Marco & Mandic, Vladimir & Ramač, Robert & Pfahl, Dietmar & Engblom, Christian & Kyykka, Jarno & Rungi, Kerli & Palomeque, Carolina & Spisak, Jaroslav & Juristo, Natalia. (2020). A Family of Experiments on Test-Driven Development.

Scanniello, G., Romano, S., Fucci, D., Turhan, B., & Juristo, N. (2016). Students’ and professionals’ perceptions of test-driven development : a focus group study. Proceedings of the 31st Annual ACM Symposium on Applied Computing, 1422‑1427. [doi](https://doi.org/10.7287/peerj.preprints.1619)

Tosun, A., Dieste, O., Vegas, S., Pfahl, D., Rungi, K., & Juristo, N. (2020). Investigating the Impact of Development Task on External Quality in Test-Driven Development : An Industry Experiment. IEEE Transactions on Software Engineering, 1. [doi](https://doi.org/10.1109/tse.2019.2949811)

Trumler, W., & Paulisch, F. (2016). How “Specification by Example” and Test-Driven Development Help to Avoid Technical Debt. 2016 IEEE 8th International Workshop on Managing Technical Debt (MTD), 1‑8. [doi](https://doi.org/10.1109/mtd.2016.10)

Unkelos-Shpigel, N., & Hadar, I. (2018). Test First, Code Later : Educating for Test Driven Development. Lecture Notes in Business Information Processing, 186‑192. [doi](https://doi.org/10.1007/978-3-319-92898-2_16)
