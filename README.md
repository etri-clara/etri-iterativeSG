# etri-iterativeSG

전상훈 박사님/최민규 학생! 제가 샘플로 만들어놓은 README입니다. 코드 올려주시고 README 보완해주세요.

# our motivation
![plot](./intro_img.png)
[1]	KHANDELWAL, Siddhesh; SIGAL, Leonid. Iterative Scene Graph Generation. arXiv preprint arXiv:2207.13440, 2022.																	
[2]	LEE, Youngwan; PARK, Jongyoul. Centermask: Real-time anchor-free instance segmentation. In: Proceedings of the IEEE/CVF conference on computer vision and pattern recognition. 2020. p. 13906-13915.																	
																		
B.P.	Backbone Parameter																	
T.P.	Total Parameter											


| Ref.   | Project Name                    | GPU   | EA | Batch | Backbone        | Detector   | B.P.   | T.P.        | α    | β    | Epoch   | [R@20/50/100](mailto:R@20/50/100) | [ng-R@20/50/100](mailto:ng-R@20/50/100) | [zR@20/50/100](mailto:zR@20/50/100) | [mR@20/50/100](mailto:mR@20/50/100) | [hR@20/50/100](mailto:hR@20/50/100) | Inference time (s) |
| ------ | ------------------------------- | ----- | -- | ----- | --------------- | ---------- | ------ | ----------- | ---- | ---- | ------- | --------------------------------- | --------------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- | ------------------ |
| [1]    | IterativeSG                     | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | \*   | 250,000 | 29.70/32.10                       | \-                                      | \-                                  | 8.0/8.8                             | 12.6/13.80                          | \-                 |
| [1]    | IterativeSG                     | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | \-      | 27.20/29.80                       | \-                                      | \-                                  | 15.70/17.80                         | 19.90/22.30                         | \-                 |
| Github | IterativeSG                     | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 21.79/27.12/29.72                 | 22.72/30.52/35.47                       | 1.34/2.74/3.84                      | 11.15/15.61/17.70                   | \-                                  | \-                 |
|        |                                 |       |    |       |                 |            |        |             |      |      |         |                                   |                                         |                                     |                                     |                                     |                    |
|        |                                 | Titan | 4  | \-    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.50 | 780,000 | 16.82/21.04/23.43                 | 17.45/23.14/26.22                       | 0.89/1.79/2.68                      | 9.08/9.91/9.91                      | \-                                  |                    |
|        |                                 | A100  | 8  | \-    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.50 | 250,000 | 15.21/19.61/22.39                 | 15.98/20.89/24.13                       | 0.00/0.45/1.34                      | 5.45/6.73/7.59                      | \-                                  |                    |
|        |                                 |       |    |       |                 |            |        |             |      |      |         |                                   |                                         |                                     |                                     |                                     |                    |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 100,000 | 19.52/24.30/27.58                 | 20.35/26.58/30.22                       | 1.34/2.21/3.79                      | 8.46/10.00/11.40                    | \-                                  | \-                 |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 150,000 | 18.10/22.91/26.41                 | 19.40/25.50/29.15                       | 0.89/1.34/2.23                      | 8.16/9.74/10.89                     | \-                                  | 0.091286           |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 160,000 | 18.17/23.11/26.58                 | 19.53/25.54/29.56                       | 1.19/2.31/3.20                      | 7.58/9.60/10.61                     | \-                                  | 0.089788           |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 170,000 | 19.12/23.99/27.58                 | 20.43/26.27/30.18                       | 1.34/2.16/3.94                      | 7.57/9.08/10.20                     | \-                                  | 0.092584           |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 210,000 | 18.82/23.68/27.08                 | 20.17/25.81/29.73                       | 1.34/1.56/3.05                      | 7.13/8.59/9.64                      | \-                                  | 0.089087           |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 220,000 | 18.76/23.53/27.09                 | 20.31/25.96/29.58                       | 1.34/3.12/3.87                      | 7.15/8.45/9.48                      | \-                                  | 0.091409           |
|        | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 18.65/23.47/27.09                 | 20.04/25.58/29.31                       | 1.34/1.79/2.16                      | 7.07/8.35/9.43                      | \-                                  | 0.090588           |
|        | IterativeSG_VoVNet              | A100  | 8  | 64    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 70,000  | 10.12/12.97/14.38                 | 10.26/14.31/17.23                       | 0.089/1.34/1.79                     | 0.623/0.768/0.854                   | \-                                  | 0.698270           |
|        |                                 |       |    |       |                 |            |        |             |      |      |         |                                   |                                         |                                     |                                     |                                     |                    |
| A      | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 19.39/23.72/26.08                 | 19.77/26.41/30.69                       | 0.74/2.98/3.42                      | 10.54/12.92/14.43                   | \-                                  | 0.100324           |
| B      | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 250,000 | 11.07/13.88/15.33                 | 11.40/15.52/18.27                       | 0.45/1.34/1.34                      | 6.49/8.15/10.19                     | \-                                  | 0.110973           |
| C      | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 250,000 | 11.28/14.28/15.75                 | 11.68/15.89/18.87                       | 0.45/0.89/1.34                      | 6.35/8.81/10.50                     |                                     | 0.112889           |
| D      | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 250,000 |                                   |                                         |                                     |                                     |                                     |                    |
| E      | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 250,000 |                                   |                                         |                                     |                                     |                                     |                    |
| F      | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 250,000 | 24.98/27.98/29.49                 | 27.06/33.32/37.54                       | 3.35/4.91/6.70                      | 10.99/13.08/14.38                   | \-                                  | 0.124565           |
| G      | IterativeSG_VoVNet99_CenterMask | A100  | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 250,000 |                                   |                                         |                                     |                                     |                                     |                    |
|        |                                 |       |    |       |                 |            |        |             |      |      |         |                                   |                                         |                                     |                                     |                                     |                    |
| A      | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 100,000 |                                   |                                         |                                     |                                     | \-                                  |                    |
| B      | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 100,000 |                                   |                                         |                                     |                                     | \-                                  |                    |
| C      | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 100,000 | 6.40/8.18/9.46                    | 6.67/9.27/11.07                         | 0.00/0.045/0.089                    | 3.34/4.25/6.25                      | \-                                  | 0.117365           |
| D      | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 100,000 | 5.61/7.38/8.53                    | 5.53/7.91/10.00                         | 0.00/0.045/0.089                    | 2.97/3.65/4.27                      | \-                                  | 0.116621           |
| E      | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 100,000 | 18.35/20.85/22.11                 | 19.43/23.92/27.05                       | 0.89/2.90/3.35                      | 7.56/9.84/10.44                     |                                     | 0.119549           |
| F      | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 100,000 | 16.91/19.09/20.14                 | 18.07/22.54/25.60                       | 0.45/2.23/2.46                      | 7.27/8.54/9.02                      | \-                                  | 0.124869           |
| G      | IterativeSG_VoVNet99_CenterMask | A100  | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 100,000 | 11.24/12.88/13.78                 | 11.88/15.00/16.98                       | 0.22/0.67/0.156                     | 4.10/4.96/5.56                      | \-                                  | 0.152235           |


| Ref. | Project Name                    | GPU   | EA | Batch | Backbone        | Detector   | B.P.   | T.P.        | α    | β    | Epoch   | AP      | AP50    | AP75    | APs    | APm     | APl     |
| ---- | ------------------------------- | ----- | -- | ----- | --------------- | ---------- | ------ | ----------- | ---- | ---- | ------- | ------- | ------- | ------- | ------ | ------- | ------- |
|      | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 12.1520 | 22.8750 | 11.1230 | 3.4600 | 7.2930  | 17.0760 |
|      | IterativeSG_VoVNet              | A100  | 8  | 64    | VoVNetV2-39-FPN | DETR       | 96.9M  | \-          | 0.07 | 0.75 | 70,000  | 6.4535  | 14.1485 | 5.1580  | 0.4496 | 2.0273  | 9.7969  |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |         |         |         |        |         |         |
| A    | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 13.4691 | 24.9608 | 12.3987 | 3.6703 | 7.9725  | 18.3340 |
| B    | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 250,000 | 7.1613  | 14.7570 | 5.9463  | 0.6114 | 2.3128  | 10.6247 |
| C    | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 250,000 | 7.4856  | 15.4565 | 6.3122  | 0.5186 | 2.5561  | 10.9742 |
| D    | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 250,000 |         |         |         |        |         |         |
| E    | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 250,000 |         |         |         |        |         |         |
| F    | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 250,000 | 24.2753 | 34.8707 | 25.5894 | 8.6716 | 14.2439 | 32.3165 |
| G    | IterativeSG_VoVNet99_CenterMask | Titan | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 250,000 |         |         |         |        |         |         |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |         |         |         |        |         |         |
| A    | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 100,000 |         |         |         |        |         |         |
| B    | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 100,000 |         |         |         |        |         |         |
| C    | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 100,000 | 4.6338  | 10.0964 | 3.8084  | 0.1029 | 0.9584  | 6.6563  |
| D    | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 100,000 | 3.8670  | 8.4700  | 3.1530  | 0.2860 | 0.7840  | 5.4020  |
| E    | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 100,000 | 13.4100 | 23.6500 | 12.7300 | 2.8400 | 4.9200  | 19.5900 |
| F    | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 100,000 | 12.9729 | 23.2963 | 12.0455 | 2.5266 | 4.7236  | 18.9786 |
| G    | IterativeSG_VoVNet99_CenterMask | A100  | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 100,000 | 7.2027  | 12.5070 | 6.7806  | 1.1368 | 2.4701  | 10.2745 |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |         |         |         |        |         |         |


| Ref. |                                 | GPU   | EA | Batch | Backbone        | Detector   | B.P.   | T.P.        | α    | β    | Epoch   | [SGMeanRecall@20](mailto:SGMeanRecall@20) | [SGMeanRecall@50](mailto:SGMeanRecall@50) | [SGMeanRecall@100](mailto:SGMeanRecall@100) |
| ---- | ------------------------------- | ----- | -- | ----- | --------------- | ---------- | ------ | ----------- | ---- | ---- | ------- | ----------------------------------------- | ----------------------------------------- | ------------------------------------------- |
|      | IterativeSG_ETRI                | A100  | 8  | 128   | ResNet-101      | DETR       | 44.5 M | 93,251,740  | 0.07 | 0.75 | 250,000 | 0.0707                                    | 0.0835                                    | 0.0943                                      |
|      | IterativeSG_VoVNet              | A100  | 8  | 64    | VoVNetV2-39-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 70,000  | 0.0623                                    | 0.0768                                    | 0.0854                                      |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |                                           |                                           |                                             |
| A    | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 250,000 | 0.1054                                    | 0.1292                                    | 0.1443                                      |
| B    | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 250,000 | 0.0649                                    | 0.0815                                    | 0.1019                                      |
| C    | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 250,000 | 0.0635                                    | 0.0881                                    | 0.1050                                      |
| D    | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 250,000 |                                           |                                           |                                             |
| E    | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 250,000 |                                           |                                           |                                             |
| F    | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 250,000 | 0.1099                                    | 0.1308                                    | 0.1438                                      |
| G    | IterativeSG_VoVNet99_CenterMask | Titan | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 250,000 |                                           |                                           |                                             |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |                                           |                                           |                                             |
| A    | IterativeSG_UBC                 | A100  | 4  | 12    | ResNet-101      | DETR       | 44.5 M | 93,251,470  | 0.07 | 0.75 | 100,000 |                                           |                                           |                                             |
| B    | IterativeSG_VoVNet39            | A100  | 4  | 12    | VoVNetV2-39-FPN | DETR       | 52.6M  | 79,102,606  | 0.07 | 0.75 | 100,000 |                                           |                                           |                                             |
| C    | IterativeSG_VoVNet57            | A100  | 4  | 12    | VoVNetV2-57-FPN | DETR       | 68.9M  | 95,362,190  | 0.07 | 0.75 | 100,000 | 0.0334                                    | 0.0425                                    | 0.0625                                      |
| D    | IterativeSG_VoVNet99            | A100  | 4  | 12    | VoVNetV2-99-FPN | DETR       | 96.9M  | 123,408,270 | 0.07 | 0.75 | 100,000 | 0.0297                                    | 0.0365                                    | 0.0427                                      |
| E    | IterativeSG_VoVNet39_CenterMask | Titan | 4  | 12    | VoVNetV2-39-FPN | CenterMask | 52.6M  | 103,168,224 | 0.07 | 0.75 | 100,000 | 0.0756                                    | 0.0984                                    | 0.1044                                      |
| F    | IterativeSG_VoVNet57_CenterMask | Titan | 4  | 12    | VoVNetV2-57-FPN | CenterMask | 68.9M  | 119,427,808 | 0.07 | 0.75 | 100,000 | 0.0727                                    | 0.0854                                    | 0.0902                                      |
| G    | IterativeSG_VoVNet99_CenterMask | A100  | 4  | 12    | VoVNetV2-99-FPN | CenterMask | 96.9M  | 147,473,888 | 0.07 | 0.75 | 100,000 | 0.0410                                    | 0.0496                                    | 0.0556                                      |
|      |                                 |       |    |       |                 |            |        |             |      |      |         |                                           |                                           |                                             |



# Iterative Scene Graph Generation

Below code is the reference paper titled ["Iterative Scene Graph Generation"](https://openreview.net/pdf?id=i0FnLiIRj6U).

## Requirements
The following packages are needed to run the code.
- `python == 3.8.5`
- `PyTorch == 1.8.2`
- `detectron2 == 0.6`
- `h5py`
- `imantics`
- `easydict`
- `cv2 == 4.5.5`
- `scikit-learn`
- `scipy`
- `pandas`

We use the Visual Genome filtered data widely used in the Scene Graph community. 
Please see the public repository of the paper  [Unbiased Scene Graph Generation repository](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/blob/master/DATASET.md) on instructions to download this dataset. After downloading the dataset you should have the following 4 files: 
- `VG_100K `directory containing all the images
- `VG-SGG-with-attri.h5` 
- `VG-SGG-dicts-with-attri.json` (Can be found in the same repository [here](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/tree/master/datasets/vg))
- `image_data.json` (Can be found in the same repository [here](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch/tree/master/datasets/vg))

## Train Iterative Model
To enable faster model convergence, we pre-train DETR on Visual Genome. We replicate the DETR decoder weights three times, and initialize our models three decoders with it. For convenience, the pretrained weights (with the decoder replication) are made available [here](https://drive.google.com/drive/folders/1CdcYdcYEvkZHz-I1IFF8sBxVMWSyWIkh?usp=share_link). To use these weights during training, simply use the `MODEL.WEIGHTS <Path to downloaded checkpoint>` flag in the training command.

Our proposed iterative model can be trained using the following command:
```python
python train_iterative_model.py --resume --num-gpus <NUM_GPUS> --config-file configs/iterative_model.yaml OUTPUT_DIR <PATH TO CHECKPOINT DIR> DATASETS.VISUAL_GENOME.IMAGES <PATH TO VG_100K IMAGES> DATASETS.VISUAL_GENOME.MAPPING_DICTIONARY <PATH TO VG-SGG-dicts-with-attri.json> DATASETS.VISUAL_GENOME.IMAGE_DATA <PATH TO image_data.json> DATASETS.VISUAL_GENOME.VG_ATTRIBUTE_H5 <PATH TO VG-SGG-with-attri.h5> MODEL.DETR.OVERSAMPLE_PARAM <Alpha Value> MODEL.DETR.UNDERSAMPLE_PARAM <Twice the Beta Value> SOLVER.CLIP_GRADIENTS.CLIP_VALUE 0.01 SOLVER.IMS_PER_BATCH 12 MODEL.DETR.NO_OBJECT_WEIGHT 0.1 MODEL.WEIGHTS <PATH TO DETR Pretrained Model>
```
To set the `α` value use `MODEL.DETR.OVERSAMPLE_PARAM` flag, and set the `β` value using the `MODEL.DETR.UNDERSAMPLE_PARAM`. Note that `MODEL.DETR.UNDERSAMPLE_PARAM` should be specified as twice the desired β value. So for `β=0.75` use `MODEL.DETR.UNDERSAMPLE_PARAM 1.5`.

**Note**: If the code fails, try running it on a single GPU first in order to allow some preprocessed files to be generated. This is a one-time step. Once the code runs succesfully on a single GPU, you can run it on multiple GPUs as well. Additionally, the code, by default, is configured to run on 4 GPUs with a batch size of 12. If you run out of memory, change the batch size by using the flag `SOLVER.IMS_PER_BATCH <NUM IMAGES IN BATCH>`.

To evaluate the code, use the following command:
```python
python train_iterative_model.py --resume --eval-only --num-gpus <NUM_GPUS> --config-file configs/iterative_model.yaml OUTPUT_DIR <PATH TO CHECKPOINT DIR> DATASETS.VISUAL_GENOME.IMAGES <PATH TO VG_100K IMAGES> DATASETS.VISUAL_GENOME.MAPPING_DICTIONARY <PATH TO VG-SGG-dicts-with-attri.json> DATASETS.VISUAL_GENOME.IMAGE_DATA <PATH TO image_data.json> DATASETS.VISUAL_GENOME.VG_ATTRIBUTE_H5 <PATH TO VG-SGG-with-attri.h5>
```
You can find our model weights for `α=0.07` and `β=0.75` [here](https://drive.google.com/drive/folders/1L2H2e-UfyKfbbmM34LaJfT6S49VTfZDY?usp=share_link). To use these weights during evaluation, simply use the `MODEL.WEIGHTS <Path to downloaded checkpoint>` flag in the evaluation command. To check if the code is running correctly on your machine, the released checkpoint should give you the following metrics on the Visual Genome test set `VG_test`.

```python
SGG eval:     R @ 20: 0.2179;     R @ 50: 0.2712;     R @ 100: 0.2972;  for mode=sgdet, type=Recall(Main).
SGG eval:  ng-R @ 20: 0.2272;  ng-R @ 50: 0.3052;  ng-R @ 100: 0.3547;  for mode=sgdet, type=No Graph Constraint Recall(Main).
SGG eval:    zR @ 20: 0.0134;    zR @ 50: 0.0274;    zR @ 100: 0.0384;  for mode=sgdet, type=Zero Shot Recall.
SGG eval:    mR @ 20: 0.1115;    mR @ 50: 0.1561;    mR @ 100: 0.1770;  for mode=sgdet, type=Mean Recall.
```

### IterativeSG
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="@inproceedings{Yu2022CoCaCC,
  title   = {Iterative Scene Graph Generation},
  author  = {Siddhesh Khandelwal and Leonid Sigal},
  year    = {NeurIPS 2022}
}"><pre class="notranslate"><code>
@inproceedings{Yu2022CoCaCC,
  title   = {Iterative Scene Graph Generation},
  author  = {Siddhesh Khandelwal and Leonid Sigal},
  year    = {NeurIPS 2022}
}
</code></pre></div>

### CenterMask
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="@inproceedings{Yu2022CoCaCC,
  title   = {enterMask: Real-Time Anchor-Free Instance Segmentation},
  author  = {Lee, Youngwan and Park, Jongyoul},
  year    = {CVPR 2020}
}"><pre class="notranslate"><code>
@inproceedings{lee2020centermask,
  title   = {enterMask: Real-Time Anchor-Free Instance Segmentation},
  author  = {Lee, Youngwan and Park, Jongyoul},
  year    = {CVPR 2020}
}
</code></pre></div>
