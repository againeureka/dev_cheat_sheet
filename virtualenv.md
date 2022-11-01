
# 개발환경 구축

- JPark
- Since Sep. 2022

## 직접 개발환경 구축해야 하는가?
- <b> 귀찮지만, 귀한일 </b>
- <b> 언젠가는 할일</b>

## 주요 명령어 요약

### pip self upgrade

```bash
    $ pip install --upgrade pip
```

### pip requirements.txt install

```bash
    $ pip install -r requirements.txt
```


### pip 설치한 패키지 확인

```bash
    $ pip list
    $ pip list | grep tensor
```

### jupyter 커널 확인

```bash
    $ jupyter kernelspec list
    $ 
```

### jupyter 커널 제거 (선확인)

```bash
    $ jupyter kernelspec list
    $ jupyter kernelspec uninstall myKernalName 
```

### jupyter 커널 

```bash
    $ jupyter kernelspec list
    $ jupyter kernelspec uninstall myKernalName 
```

### conda 환경 확인

```bash
    $ conda env list
    $ 
```







## 가상환경 생성/진입/패키지 설치 (빠른 활용)

**NOTE:**
- 일반 python 기준으로 예시 방법을 제시합니다. 
- python3 기준입니다.
- Anaconda와 같은 다른 패키지 관리도구를 사용하는 경우 방법이 다를 수 있습니다.


- 참고 주소

```bash
https://ipython.readthedocs.io/en/stable/install/kernel_install.html
```

- 가상환경을 만듭니다.
- 가상환경이 친숙하지 않더라도 <b>"필수"</b>라고 생각합니다.
- 웹에서 다운로드 받은 코드가 잘 작동하지 않을 경우, 많은 경우 가상환경 생성을 통해 문제를 해결할 수 있습니다 (대부분 패키지 버전 불일치가 원인)


```bash
    $ pip3 install virtualenv
    $ python3 -m virtualenv venv_nlp 
```

- 생성한 가상환경에 진입합니다.
- 이곳은 이제 Python 개발을 위한 자신만의 <b>"우주"</b>입니다.
- 원하는 모든 패키지를 자유롭게 설치하고 지울수 있는 <b>자유로운 </b>입니다.

```bash
    $ source venv_nlp/bin/activate
```

- 가상환경을 나가는 것도 자유입니다.

```bash
    $ deactivate
```


- 하지만 우리는 jupyter lab을 설치해야 하므로 가상환경에 다시 들어옵니다.

```bash
    $ source venv_nlp/bin/activate
```


- 일부 꼼꼼한 분들은 가상환경이 어떤 python 버전을 쓰고 있는지 아래와 같은 명령어로 확인하기도 합니다.

```bash
    $ which python3
    or 
    $ which python 
```


- 내가 설치한 패키지가 다른 프로젝트를 망칠수도 있겠다는 걱정은 이제 필요 없습니다.
- 가상환경에 의존성 패키지를 설치하는데 주저하지 않습니다.

```bash
    $ pip3 install -r requirements.txt
```


- 혹은 패키지를 낱개 단위로 설치할 수도 있습니다.

```bash
    $ pip3 install -r numpy
```


## 가상환경을 Jupyter에 커널로 연결

- 다시 가상환경에 진입합니다.


```bash
    $ source venv_nlp/bin/activate
```

- 'jupyter lab'도 설치합니다.
- 이제 <b>"나의 우주"</b>에  <b>"나의 실험실"</b>이 생깁니다.

```bash
    $  pip install jupyterlab
```

- 새로 설치한 jupyter lab에는 우리의 "가상우주(가상환경)"를 아직은 볼 수 없습니다.
- 아래와 같은 명령어로 ipykernel 설치하고 우리의 가상환경을 kernel 목록에 등록해야 합니다.

```bash
    $ pip install ipykernel
    $ python3 -m ipykernel install --user --name venv_nlp --display-name "venv_nlp"
```

- 이제 jupyter lab에 우리가 생성한 "venv_nlp"라는 가상환경이, "venv_nlp"이라는 이름으로 나타납니다.
- 당연히 ipykernel 로 생성한 kernel이나 가상환경을 지울 수도 있습니다.
- 지우는 법은 웹 검색을 통해 쉽게 알 수 있습니다.

![env](img4doc/env.png)












## (참고) 원하는 python 버전의 가상환경 설치

- 이렇게 하면 2.7 버전에서 개발을 수행할 수 있습니다.

```bash
    $ python -m virtualenv venv_nlp --python=python2.7
```

- 당연히 3.7 버전 설치와 같은 시도도 가능합니다.
- 물론 자신의 컴퓨터에 python3.7 버전이 설치되어 있지 않다면 에러가 발생할 수는 있을 겁니다.

```bash
    $ python -m virtualenv venv_nlp --python=python3.7
```



## (선택사항) Mac OS에서 개발하신다면 ?

- 아래와 같은 방법을 참고하실 수도 있습니다.
- 참고 : https://willbesoon.tistory.com/145

```bash
    $ conda create -n base python=3.8
    $ jupyter kernelspec list
    $ conda activate base
    $ conda install ipykernel
    $ conda env list
    $ /opt/homebrew/Caskroom/miniforge/base/bin/python3 -m ipykernel install --user --name base --display-name "base(conda)"

```



## (참고) Anaconda vs. Miniconda

- 참고 : https://pythonnumericalmethods.berkeley.edu/notebooks/chapter01.01-Getting-Started-with-Python.html
- Anaconda : 기본 python + 설치 도구 제공, 주요 패키지 포함
- Minconda : 기본 python + 설치 도구 제공, 패키지는 직접 설치 해야함 

