# Polygame AI: Multi-Task Deep Reinforcement Learning in Atari
This research explores advancements in multi-task reinforcement learning by modifying the Deep Q-Network algorithm to develop Polygame AI, capable of learning to play multiple Atari games. Our approach demonstrates the potential for scalable learning across diverse and complex tasks.

## Poster
![Polygame AI Poster](https://github.com/user-attachments/assets/a81a4425-1919-41e6-a218-60f55c2484bf)

## Introduction
Despite the fact that improvements and research in machine learning models and artificial intelligence are on the rise, the versatility of these models is still yet to reach its full potential. Specifically, multitasking is an area in need of major improvement, as it would allow for a single model to complete a multitude of tasks by training it only once on all necessary datasets simultaneously. Such an achievement could eliminate the need for having multiple models for similar tasks and instead only require having a single model trained for multitasking. Deployed onto Atari games, containing environments of generally similar actions, Polygame AI aims to prove that reinforcement learning can be used to attain the versatility we seek in a multi-task model.

## Dataset
The Atari Gymnasium Library provides every environment. Each action space is discrete, choosing actions based on the greatest action space we work with. All environments have the same observation space of 160x210 pixels with three channels for the RGB coloring scale. Data provided by the observation space is a stack of four frames instead of one to allow the agent to understand the movement in the game. We rescale the frame stack to be 84x84 pixels and grayscale it to reduce the complexity of the data.

We scale all rewards between ‐1 and 1 to allow our agent to improve run consistency between different games. Since each game has varying sizes of rewards, greater rewards would make it harder to train for multiple games since it could overweigh specific actions.

## Model
We utilize a Deep Q-Network with three convolutional layers and two linear layers. The number of output nodes is set to be the maximum action space of the set of games that the model is being trained on.

![Model White](https://github.com/user-attachments/assets/0388b732-8733-4905-b12a-7d4cb9b3387e)

## Results
Throughout our training of DQN agents on two Atari games, we observed fluctuations in the return as the agents explored their environments. However, with an increasing number of executed steps, we saw consistent growth in the cumulative rewards across all games. The following graphs illustrate this trend, plotting the agents’ cumulative rewards against the number of steps for Atari Breakout and Space Invaders.

<div align="center">
  <img height="219" alt="Breakout Results" src="https://github.com/user-attachments/assets/11dd8726-3a09-40f5-b15e-a24601bec61a">
  <img height="219" alt="Space Invaders Results" src="https://github.com/user-attachments/assets/5fe5fc96-a979-49f1-9c90-809ccffeb4b8">
</div>

## Conclusion
By training our agent on two Atari games, we observed its ability to adapt to a multi‐environment scenario. Since we only have results for two Atari games, we cannot conclude that our algorithm would be scalable. However, the results we have observed so far have shown that reinforcement learning could lead to promising advancements in multi-task learning, which can impact domains such as robotics, autonomous vehicles, and personalized medicine, which requires models with high adaptability and a broad range. Our next steps are to expand our agent to handle more Atari games and delve into other domains, such as previously mentioned.

## Contributors
- [Artan Vafaei](https://github.com/ArtanVafaei)
- [Earl Velasquez](https://github.com/Evelas78)
- [Lalith Vennapusa](https://www.linkedin.com/in/lalith-vennapusa-90812323a/)
- [Aldrin Roshan](https://www.linkedin.com/in/aldrinroshan/overlay/photo/)
- [Sowresh Mecheri-Senthil](https://github.com/SowreshMS) - Research Lead
- [Dr. Anjum Chida](https://profiles.utdallas.edu/anjum.chida) - Faculty Advisor

## References
[1]  Antonoglou, I., Graves, A., Kavukcuoglu, K., Mnih, V., Silver, D., Riedmiller, M., Wierstra, D., (2013). Playing Atari with Deep Reinforcement Learning. arXiv preprint arXiv:1312.5602.

[2] Czarnecki, W., Espeholt, L., Hessel, M., Schmitt S., Soyer, H., & van Hasselt, H. (2018). Multi‐task Deep Reinforcement Learning with PopArt. arXiv preprint arXiv:1809.04474.

[3] Espeholt et al, IMPALA: Scalable Distributed Deep‐RL with Importance Weighted Actor‐Learner Architectures, ICML 2018.
