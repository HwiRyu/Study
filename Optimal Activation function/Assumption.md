# What is optimal activation function

최근들어 Relu의 변형, Relu와 비슷하지만 Relu의 장점을 취하고 Relu에는 없는 성질을 더한 Swish과 같은 다양한 Activation function이 나오고 있다. 무엇이 좋은 Activation function일까.

# Background

Relu가 사랑받는건 다양한 이유가 있지만 치역이 [0,$\infin$]으로 saturation되지 않아 gradient flow에 적합하며, 단순하다.
input data에 대해 0보다 크면 input을 그대로 output하고, 0보다 작으면 그냥 0을 output한다. 이 단순성 덕분에 빠른 계산속도를 취할 수 있으며, 다양한 model과 dataset에 대해 높은 신뢰도를 보인다. 

$\theta$가 trainable한 parameter이고, 어떤 함수 $f$가 continous하다면 Relu를 Activation function으로 사용한 FNN으로 $f(x;\theta) \rightrightarrows f$ 되도록 하는 신경망 $f(x;\theta)$ 가 존재한다. 여기서 FNN의 hidden layer를 여러개 쌓는다면, layer의 일부분도 각각 어떤 함수를 표현할 수 있을 것이고, 이때 신경망 $f(x;\theta)$안의 이어져있는 어떤 layer들이 이루는 함수 $L(x; \theta \in X)$ 또한 충분한 $\theta$가 존재하면 어떤 연속함수에 대해 충분히 근사시킬 수 있다.

즉 어떤 함수를 Activation function으로 사용하더라도, parameter가 충분하다면 Relu layer로 어떤 Activation function사용한 것과 같이 근사시킬 수 있다.

그러나 Relu를 통해 다른 Activation function을 사용한 것과 같은 solution이 존재하는 것과 learning을 통해 그 solution을 찾아낼 수 있느냐는 다른 문제다.

# Assumption

Relu가 가장 Optimal한 Activation function이다.

즉, 어떤 Activation function을 사용해도 Relu를 통해 gradient method로 같은 효과를 내도록 학습시킬 수 있으며, 계산도 더 빠를 것이다.

이 가정이 참인지 거짓인지를 지금부터 공부한다.