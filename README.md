## Santiago Zubieta
#### 2018

*'I was caught in the middle of a railroad track,
I looked around and I knew there was no turning back'*  
-ACDC, Thunderstruck

## Spark And Python For Big Data With PySpark
These are codes and data made for or provided by the **Spark And Python For Big Data With Pyspark** course by **Pierian Data / Jose Portilla** at [Udemy](https://www.udemy.com/spark-and-python-for-big-data-with-pyspark/), which I'm taking in my free time seeking to understand more about data science and modern tools used to work on it. Please do not copy
if you are taking the course :-D For all other purposes, my files are under the **MIT License**.

## Apache Spark Setup in Ubuntu VM:

1. Install Virtual Box.
2. Get .iso for `ubuntu-18.04.1-desktop-amd64`, it is the LTS version.
3. Once it's finalized installing, do:
	* `$ sudo apt-get update`
	* `$ sudo apt-get upgrade`
4. Set up the git repository with SSH key access.
        * `$ sudo apt-get install git`
        * Read [https://docs.gitlab.com/ee/ssh/#adding-an-ssh-key-to-your-gitlab-account](https://docs.gitlab.com/ee/ssh/#adding-an-ssh-key-to-your-gitlab-account)
        * `$ git clone git@gitlab.com:zubie7a/Spark_And_Python_For_Big_Data`
        * `$ git config --global user.name 'Santiago Zubieta'`
        * `$ git config --global user.email 'santiago.zubieta@gmail.com'`
4. In top-bar select "Insert Guest Additions CD Image"
5. Install, then make **Shared Clipboard** and **Drag and Drop** be **bidirectional**.
6. Create a Shared Folder for ease of file transfer.
7. To be able to access the Shared Folder without giving password always, do:
	* `$ sudo add user zubieta vboxsf`
8. Check Python3 version (Ideally 3.6.5)
	* `$ sudo apt-get install python3-pip`
9. Check Pip version with
	* `$ pip3 -V`
10. Install Jupyter
	* `$ pip3 install jupyter --user` 
11. Install Pipenv
	* `$ pip3 install pipenv --user` *(just in case).*
12. Install Py4j
	* `$ pip3 install py4j --user`
13. Install Java 
	* `$ sudo apt-get install openjdk-8-jre`
    * Remember that it must be **Java 8** for all of this to work.
    * The path will be `/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin/java`
    * `$ java -version` : `'openjdk version "1.8.0_181"`
14. Install Scala `$ sudo apt-get install scala`
    * `$ scala -version` : `'Scala code runner version 2.11.12'`
15. Download [Spark](https://spark.apache.org/downloads.html):
    * `spark-2.3.1-bin-hadoop2.7.tgz`
    * Decompress it `$ sudo tar -zxvf spark-2.3.1-bin-hadoop2.7`
    * Give permissions to all necessary folders:
        - ` $ sudo chmod 777 spark-2.3.1-bin-hadoop2.7/`
        - ` $ cd spark-2.3.1-bin-hadoop2.7/`
        - ` $ sudo chmod 777 python/`
        - ` $ cd python/`
        - ` $ sudo chmod 777 pyspark/`
16. Add to PATH the pip local path and env variables for Spark
    * ```
        export PATH="~/.local/bin:$PATH"
        export SPARK_HOME='/home/zubieta/spark-2.3.1-bin-hadoop2.7'
        export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
        export PYSPARK_DRIVER_PYTHON='jupyter'
        export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
        export PYSPARK_PYTHONPATH=python3
        export PYSPARK_PYTHON=python3
        export JAVA_HOME='/usr/lib/jvm/java-1.8.0-openjdk-amd64/'
        export PATH=$SPARK_HOME:$PATH:$JAVA_HOME/bin:$JAVA_HOME/jre/bin
      ```
17. Open a notebook with `$ jupyter notebook`
18. Create a new Jupyter Notebook:
    * ![/Resources/Images/Jupyter_Create_Notebook.png](https://i.imgur.com/ZwrexH1.png "")
19. Try importing pyspark inside the notebook:
    * `import pyspark`
    * If doesn't work you need to be inside:
	*`spark-2.3.1-bin-hadoop2.7/python/`
    * Else, you need FindSpark to be able to import Spark from elsewhere.
    * Install FindSpark:
	* `$ pip3 install findspark --user`
    * To find spark, do this in the Python notebooks:
        * ```python
            import findspark
            findspark.init('/home/zubieta/spark-2.3.1-bin-hadoop2.7')
            import pyspark 
        ```
