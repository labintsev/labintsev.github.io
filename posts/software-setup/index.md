<!--
.. title: Настройка программного обеспечения 
.. slug: software-setup
.. date: 2025-03-01 19:42:16 UTC+03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
.. has_math: true
-->

# Настройка программного обеспечения  
  
В этом году рекомендуется работать над заданиями через [Google Colaboratory](https://colab.research.google.com/). Однако, если у вас уже есть оборудование на базе графического процессора и вы предпочитаете работать локально, мы предоставим вам инструкции по настройке виртуальной среды.
- [Удаленная работа в Google Colaboratory]()
- [Работа локально на вашем компьютере]()
    - [Виртуальная среда Anaconda]()
    - [Python venv]()
    - [Установка пакетов]()
  
  
### Удаленная работа в Google Colaboratory  
  
*Google Colaboratory* — это, по сути, комбинация *Jupyter notebook* и* Google Drive*. Он полностью работает в облаке и поставляется предустановлены многие пакеты (например, *PyTorch* и *Tensorflow*), поэтому у всех есть доступ к одному и тому же Зависимости. Еще круче тот факт, что Colab получает бесплатный доступ к аппаратным ускорителям например, графические процессоры (*K80*, *P100*) и ТПУ, которые будут особенно полезны для заданий **2** и **3**.  
  
__Требования__. Чтобы использовать *Colab*, у вас должен быть аккаунт *Google* со связанным *Google* **Диском**. Предполагая, что у вас есть и то, и другое, вы можете подключить *Colab* к диску, выполнив следующие действия:

1. Нажмите на колесико в правом верхнем углу и выберите .`Settings`
2. Нажмите на вкладку.`Manage Apps`
3. Вверху выберите, что должно вызвать окно.`Connect more apps` `GSuite Marketplace`
4. Найдите __Colab__ и нажмите .`Add`  
 

__Рабочий процесс__. Каждое задание содержит ссылку для скачивания zip-файла, содержащего записные книжки *Colab* и начальный код *Python*. Вы можете загрузить папку на **Диск**, открыть записные книжки в *Colab* и работать с ними, а затем сохранить свой прогресс обратно на **Диск**. Мы рекомендуем вам посмотреть обучающее видео ниже, в котором описывается рекомендуемый рабочий процесс на примере задания **1**.  
  
<iframe style="display: block; margin: auto;" width="560" height="315" src="https://www.youtube.com/embed/DsGd2e9JNH4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    
    
__Лучшие практики__. Есть несколько вещей, о которых вы должны знать при работе с *Colab*. Первое, что стоит отметить, это то, что ресурсы не гарантируются (это плата за бесплатность). Если вы бездействуете в течение определенного времени или общее время подключения превышает максимально допустимое время (*~12 часов*), виртуальная машина *Colab* будет отключена. Это означает, что любой несохраненный прогресс будет потерян. <font color="red"><strong> Таким образом, выработайте привычку часто сохранять свой код во время работы над заданиями. </strong></font> Чтобы узнать больше об ограничениях ресурсов в *Colab*, ознакомьтесь с их часто задаваемыми вопросами [здесь](https://research.google.com/colaboratory/faq.html).

__Использование графического процессора__. Использовать графический процессор так же просто, как переключить среду выполнения в *Colab*. В частности, нажмите, и ваш экземпляр *Colab* будет автоматически подкреплен вычислениями графического процессора.`Runtime -> Change runtime type -> Hardware Accelerator -> GPU`  
  
Если вы хотите узнать больше о *Colab*, мы рекомендуем вам посетить следующие ресурсы:
- [Введение в Google Colab](https://www.youtube.com/watch?v=inN8seMm7UI)
- [Добро пожаловать в Colab](https://colab.research.google.com/notebooks/intro.ipynb)
- [Обзор функций Colab](https://colab.research.google.com/notebooks/basic_features_overview.ipynb)  
  

### Работа локально на вашем компьютере  
  
Если вы хотите работать локально, вам следует использовать виртуальную среду. Вы можете установить его через *Anaconda* (рекомендуется) или через собственный модуль *Python*. Убедитесь, что вы используете **Python 3.7**, так как __мы больше не поддерживаем Python 2__.`venv`  
  
#### Виртуальная среда Anaconda
Мы настоятельно рекомендуем использовать бесплатный [дистрибутив Anaconda Python](https://www.anaconda.com/download/), который предоставляет простой способ обработки зависимостей пакетов. Пожалуйста, обязательно скачайте версию **Python 3**, которая в настоящее время устанавливает **Python 3.7**. Приятная вещь в *Anaconda* заключается в том, что она поставляется с [оптимизацией MKL](https://docs.anaconda.com/mkl-optimizations/) по умолчанию, что означает, что вы и код получаете значительное ускорение без необходимости изменять ни одной строки кода.`numpy` `scipy`

После установки Anaconda имеет смысл создать виртуальную среду для курса. Если вы решите не использовать виртуальную среду (*настоятельно не рекомендуется!*), вы должны убедиться, что все зависимости для кода установлены глобально на вашем компьютере. Чтобы настроить виртуальную среду с именем , выполните следующие действия в терминале:`cs231n`  
  
```
# this will create an anaconda environment
# called cs231n in 'path/to/anaconda3/envs/'
conda create -n cs231n python=3.7
Чтобы активировать и войти в среду, запустите . Чтобы отключить среду, запустите терминал или выйдите из него. Обратите внимание, что каждый раз, когда вы хотите поработать над заданием, вы должны повторно запустить .conda activate cs231nconda deactivate cs231nconda activate cs231n

# sanity check that the path to the python
# binary matches that of the anaconda env
# after you activate it
which python
# for example, on my machine, this prints
# $ '/Users/kevin/anaconda3/envs/sci/bin/python'
``` 
  
  
Вы можете обратиться к [этой странице](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) за более подробными инструкциями по управлению виртуальными средами с помощью Anaconda.  
  
__Заметка___: Если вы решили пойти по пути *Anaconda*, вы можете смело пропустить следующий раздел и сразу перейти к [установке пакетов](https://cs231n.github.io/setup-instructions/#installing-packages).  
  
### Python venv  
  
Начиная с версии *3.3*, *Python* поставляется с облегченным модулем виртуальной среды под названием [venv](https://docs.python.org/3/library/venv.html). Каждая виртуальная среда упаковывает свой собственный независимый набор установленных пакетов *Python*, которые изолированы от общесистемных пакетов *Python* и запускают версию *Python*, совпадающую с версией двоичного файла, который использовался для ее создания. Чтобы настроить виртуальную среду с именем , выполните следующие действия в терминале:`cs231n`  
  
 
```
# this will create a virtual environment
# called cs231n in your home directory
python3.7 -m venv ~/cs231n
``` 
  
  
Чтобы активировать и войти в среду, запустите . Чтобы отключить среду, запустите терминал или выйдите из него. Обратите внимание, что каждый раз, когда вы хотите поработать над заданием, вы должны повторно запустить .`source ~/cs231n/bin/activate` `deactivate` `source ~/cs231n/bin/activate`  
  
```
# sanity check that the path to the python
# binary matches that of the virtual env
# after you activate it
which python
# for example, on my machine, this prints
# $ '/Users/kevin/cs231n/bin/python'
```
  
  
### Установка пакетов  
  
После того как вы __настроили__ и __активировали__ свою виртуальную среду (с помощью или ), вы должны установить библиотеки, необходимые для выполнения назначений с помощью . Для этого выполните:`conda` `venv` `pip`
  
  
```
# again, ensure your virtual env (either conda or venv)
# has been activated before running the commands below
cd assignment1  # cd to the assignment directory

# install assignment dependencies.
# since the virtual env is activated,
# this pip is associated with the
# python binary of the environment
pip install -r requirements.txt  
```