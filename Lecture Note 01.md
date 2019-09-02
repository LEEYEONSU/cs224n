## Introduction
#### Lecture Plan 
- 기본적인 인간의 언어
- Word2Vec 
- Gensim

1. Course
	> In cs224n we can learn 
	- attention과 같은 최근 deep learning 기법들을 이해할 수 있다.
		- 사람의 언어가 왜 이해하기 어려운지 알고 어떻게 생산하고 이해해야할지 알 수 있다.
		- PyTorch를 이용하여 자연어처리의 여러가지 문제들을 해결할 능력을 기를 수 있다.

2. Human language and word meaning
	> How do we represent the meaning of a word?
	- denotational semantics
		- signifier(symbol) \<-\> signified(idea or things)
			- ￼file:///.file/id=6571367.6755867
	> How do we have usable meaning in a computer?
	- Computer는 의미를 인식하는 방법 중 하나로 WordNet을 사용한다.
		- Wordnet = [https://ko.wikipedia.org/wiki/%EC%9B%8C%EB%93%9C%EB%84%B7][1] 영어의 의미 어휘목록이다.
			- ‘sysnet’이라는 유의어 집단으로 분류하여 간략하고 일반적인 정의를 제공하고, 어휘목록 사이의 다양한 의미 관계를 기록한다. 
				￼file:///.file/id=6571367.6756133
	- Problems with resources like WordNet
		- Wordnet은 문제점이 있다.
			- 어감이나 숨겨진 의미 인식이 어렵다.
			- 문맥의 의미를 따지지않고 단어를 보기때문에 문맥에 따라 바뀌는 언어의 의미를 제대로 파악하지 못한다.
			- 최신정보 유지가 어렵다. 
				- 사전을 업데이트 하지않는다면,,,
			- 사람이 기록하기 때문에 주관성이 개입되고, 단어 유사성을 정확하게 계산해내지 못한다.
	- Representing words as discrete symbols
		- one-hot vectors
			- ex) motel = [000000010]() , hotel = [0001000000][3]
		- 위의 one-hot vectors 형태와 같이 discrete하게 단어를 표현한다면 motel과 hotel은 전혀 관계없다는 식으로 orthogonal하게 인식된다. 
		- 위의 문제점을 개선하기 위해 vectors자체를 유사성으로 표현하는 시도를 하게 되고 Word2vec라는 개념이 도입된다. (Learn to encode similarity in the vectors themselves)
		- Word2vec이 도입되기 위한 핵심적인 개념은 단어의 의미를 파악하기 위해 window size를 가지고 주변의 단어들을 본다는 것이다. 
			- 여기서 나오는 Distributional semantics = ‘ 비슷한 위치에서 등장하는 단어들은 비슷한 의미를 가진다’ 
				- ex) 강아지는 귀엽다, 강아지는 예쁘다, 강아지는 사랑스럽다 
					- 이 부분에서 귀엽다, 예쁘다, 사랑스럽다가 유사한 의미를 가진다고 보는 것
			- 주변단어 (context)를 고려하여 symbol자리와 비슷한 품사나 의미를 가진 단어를 예측하는 것이다. (When a word W appears in a text, its _context_ is the set of words that appear nearby.
			- “You shall know a word by the company it keeps.”
			- symbol = one-hot encoding , distributional representation = word Embedding
			- Word vectors
				- word vectors = Word Embeddings or word representation -\> They are distributed representation.
			- Word meaning as a neural word vector - visualization
			- file:///.file/id=6571367.6756508

3. Wordevec : Overview
	> CBOW 방식
	- 주변단어로 중심단어를 예측하는 방식 
	> Skip - Gram 방식 
	- 중심단어로 주변단어를 예측하는 방식 
		- CBOW보다 학습을 개선 할 수 있는 횟수가 많기 때문에 성능이 좋다고 알려졌다. 
[	\> Word2vec을 이해하기 위한 ratsgo’s blog ][4]

[1]:	https://ko.wikipedia.org/wiki/%EC%9B%8C%EB%93%9C%EB%84%B7
[3]:	]
[4]:	https://ratsgo.github.io/from%20frequency%20to%20semantics/2017/03/30/word2vec/