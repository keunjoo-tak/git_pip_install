# git_pip_install
This repo is made for test about Python pip install with github

# __init__
해당 Python환경이 패키지라는 것을 알려줌. init.py에서는 Python package에서 사용하는 파일들의 정보를 담아주면 됨. 자세한 것은 아래 예시 참고

# setup.py
pip install을 할 때 사용되는 Python package setup 정보. name, description, version 등을 포함

## (Example) __init__.py
from .tkj import *          # tkj.py 라는 Python 파일에서 각종 정보를 가져오도록 init에 구성

## (Example) tkj.py
def print_tkj(msg):
    print(f"안녕하세요? 탁근주입니다. {msg}")           # 매개변수로 msg를 받아 출력해주는 print_tkj라는 함수가 존재.

## (Example) requirement.txt
numpy==1.18.3               # 해당 Python package에 필요한 다른 라이브러리들이 있는 경우, 그 라이브러리가 설치되어야 해당 패키지가 정상적으로 설치되기 때문에 requirements.txt파일을 이용

## (Example) set.py
from setuptools import setup

setup(
    name = 'tkj_lib',       #Package의 이름
    version = '0.0.1',       #Package의 버전
    description = 'keunjoo pip install test',
    url = 'https://github.com/keunjoo-tak/git_pip_install.git',       #github repo url
    author = 'takkeunjoo',
    author_email = 'xkrrmswn@gmail.com',
    license = 'keunjoo',
    packages = ['tkj_lib'],
    zip_safe = False,
    install_requires = [
        'numpy==1.18.3'
    ]       #필요한 library들을 명시
)               # Python package에 대한 내용을 담아둠. 해당 파일에는 다양한 인자값을 넣을 수 있는데, 특히 name과 url, version, install_requires는 중요한 부분임