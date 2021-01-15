# Lesson 1+2 (Software Engineering Practice)

#### Write a modular code
* Use meaningful names:

    * **Be descriptive and imply type** - E.g. for booleans, you can prefix with `is_` or `has_`. You can also use part of speech to imply types, like verbs for functions and nouns for variables.

    * **Be consistent but clearly differentiate** - E.g. `age_list` and `age` is easier to differentiate than `ages` and `age`.

#### Refactoring code
* you use numby to make the comblixity low because numby is based on vectors so its more consistent to implement operation in numby insted of using for loops for ex .

* implement the algrathims to simplify your complexity 

* Renaming Columns:

```python
df = pd.read_csv('winequality-red.csv')
df.column = [label.replace(' ' , '_') for label in df.column]
```
* finding the intersection of two arrays:

```python
np.intersect1d(recent_books, coding_books)    #First way(Fast)
set(recent_books).intersection(coding_books)    #Second way(Faster)
```
* select all the element in a numpy array then perform an operations on them:

```python
otal_price = (gift_costs[gift_costs < 25]).sum() * 1.08
```
#### Documentations

1. In-line comment
2. [Doctring](https://numpydoc.readthedocs.io/en/latest/format.html)
3. READme files that we enclude a discription for our project in it

#### Version Control

#### Testing
* [TEST DRIVEN DEVELOPMENT(1)](https://engineering.pivotal.io/post/test-driven-development-for-data-science/)
[TEST DRIVEN DEVELOPMENT(2)](https://medium.com/uk-hydrographic-office/test-driven-development-is-essential-for-good-data-science-heres-why-db7975a03a44)
: a development process where you write tests for tasks before you even write the code to implement those tasks.(its the most conse)

* ***UNIT TEST***: a type of test that covers a “unit” of code, usually a single function, independently from the rest of the program
    * **Unit Test Advantages and Disadvantages**:
    ZThe advantage of unit tests is that they are isolated from the rest of your program, and thus, no dependencies are involved. They don't require access to databases, APIs, or other external sources of information. However, passing unit tests isn’t always enough to prove that our program is working successfully. To show that all the parts of our program work with each other properly, communicating and transferring data between them correctly, we use *integration tests*. In this lesson, we'll focus on unit tests; however, when you start building larger programs, you will want to use integration tests as well.

    * **pytest library**
    1.Create a test file starting with `test_`
    2.Define unit test functions that start with `test_` inside the test file
    3.Enter pytest into your terminal in the directory of your test file and it will detect these tests for you!


# Lesson 3 (Object-Oriented Programming)
* [every opject has 2 essential parts](screen-shot-2018-07-19-at-4.05.25-pm.png) :
    1. **Attributes**(Nouns) : a descriptor or characteristic. Examples would be color, length, size, etc
    2. **Methods**(Verbs) : an action that a class or object could take

* 1. [Class](Clsses_And_Object.png) : a blueprint consisting of methods and attributes
  2. Object : an instance of a class 

* Dockstring:
    ```python
    class Pants:
    """The Pants class represents an article of clothing sold in a store
    """

    def __init__(self, color, waist_size, length, price):
        """Method for initializing a Pants object

        Args: 
            color (str)
            waist_size (int)
            length (int)
            price (float)

        Attributes:
            color (str): color of a pants object
            waist_size (str): waist size of a pants object
            length (str): length of a pants object
            price (float): price of a pants object
        """

        self.color = color
        self.waist_size = waist_size
        self.length = length
        self.price = price

    def change_price(self, new_price):
        """The change_price method changes the price attribute of a pants object

        Args: 
            new_price (float): the new price of the pants object

        Returns: None

        """
        self.price = new_price

    def discount(self, percentage):
        """The discount method outputs a discounted price of a pants object

        Args:
            percentage (float): a decimal representing the amount to discount

        Returns:
            float: the discounted price
        """
        return self.price * (1 - percentage)
    ```

#### [Gaussian Distribution](Gaussian_distribution.jpg)

* μ = n * p    (mean)
* σ^2 = n * p * (1 - p)    (variance)
* σ = sqrt{n * p * (1 - p)}    (standard deviation)
* [probability density function](probability_density_function.jpg)

#### Installing a Package
* A Python module is just a Python file containing code.
* if want to install a package you must use the `pip`(python package manager) like so -> `pip install numpy`
* in the same level of the our folder we make a `setup.py` which is necessary for pip installing and contain the package naming,vesion,description,et cetera
* With an environment manager(AND package manager like Conda) , you can install
packages on your computer without affecting your main Python installation.
to use conda:
```
conda create --name environmentname
source activate environmentname
conda install numpy
```
-------------------
# Lesson 4 (Deep Composer)
* [Why AWS? ](what_can_AWS_do.jpg)
* [Amazon Code Guru](aws-mle-code-guru.jpg)
* [Types Of ML](types-of-ml.jpg)
* Generative AI is a part of unsupervised learning wich provide practical applications emerging across industries, from turning sketches into images for accelerated product development, to improving computer-aided design of complex objects. It takes two neural networks against each other to produce new and original digital works based on sample inputs.

* A **generator** is a convolutional neural network (CNN) that learns to create new data resembling the source data it was trained on.

* The **discriminator** is another convolutional neural network (CNN) that is trained to differentiate between real and synthetic data.
 (discriminator iteratively gets better at learning to differentiate real data from the newly created data.)

* The **generator** and the **discriminator** are trained in alternating cycles such that the generator learns to produce more and more realistic data while the discriminator iteratively gets better at learning to differentiate real data from the newly created data 

* AWS Deep Composer uses Generative AI, or specifically Generative Adversarial Networks (GANs), to generate music. GANs pit 2 networks, a generator and a discriminator, against each other to generate new content.
GANs is Similar to an [Orchestra and a Conductor](aws-mle-orchestra-metaphor.jpg): The More They Work Together, the Better They Can Perform!

* Each iteration of the training cycle is called an [*epoch*](aws-mle-gan-model.jpg). The model is trained for thousands of epochs

* [**Loss Functions**](screen-shot-2020-05-02-at-7.18.44-pm.png) : 
In machine learning, the goal of iterating and completing epochs is to improve the output or prediction of the model. Any output that deviates from the ground truth is referred to as an error. The measure of an error, given a set of weights, is called a loss function. Weights r  epresent how important an associated feature is to determining the accuracy of a prediction, and loss functions are used to update the weights after every iteration. Ideally, as the weights update, the model improves making less and less errors. Convergence happens once the loss functions stabilize;Over time, the loss functions stabilizes to a point, we call this *convergence*. This convergence can be zero, but doesn’t have to be.

* [How DeepComposer works?](aws-mle-under-hood-v2.jpg) : 
    1. Input melody captured on the AWS DeepComposer console
    2. Console makes a backend call to AWS DeepComposer APIs that triggers an execution Lambda.
    3. Book-keeping is recorded in Dynamo DB.
    4. The execution Lambda performs an inference query to SageMaker which hosts the model and the training inference container.
    5. The query is run on the Generative AI model.
    6. The model generates a composition.
    7. The generated composition is returned.
    8. The user can hear the composition in the console.
    9. The user can share the composition to SoundCloud.

* [Training Architecture](aws-mle-train-arch.png):
    1. User launch a training job from the AWS DeepComposer console by selecting hyperparameters and data set filtering tags
    2. The backend consists of an API Layer (API gateway and lambda) write request to DynamoDB
    3. Triggers a lambda function that starts the training workflow
    4. It then uses AWS Step Funcitons to launch the training job on Amazon SageMaker
    5. Status is continually monitored and updated to DynamoDB
    6. The console continues to poll the backend for the status of the training job and update the results live so users can see how the model is learning


