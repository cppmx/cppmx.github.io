---
layout: post
type: article
title: UML and videogames
date: 2020-09-12 11:00:00 -0500
categories: videogames
author: Carlos Colón
short: Understand UML class diagrams and their relationship to video games
tags: videogames,UML,patterns,software,development,java
---
# Class
Design patterns are usually best explained through the use of class diagrams, as you're able to give a demonstration of the idea while remaining abstracted. Let's consider the following class:

{% highlight java linenos %}
class Enemy
{
    public:
        void GetHealth(void) const;
        void SetHealth(int);
    private:
        int currentHealth;
        int maxHealth;
};
{% endhighlight %}

Converted to UML, it would look something like this:

![UML representation of Enemy class]({{ 'images/posts/uml/01.jpg' | absolute_url }})

Basic UML diagrams consist of three boxes that represent classes and the data that they contain. The top box is the name of the class.
Going down, you'll see the properties or variables the class will have (also referred to as the data members) and then in the bottom box
you'll see the functions that it will have. A plus symbol (+) to the left of the property means that it is going to be public, while a
minus symbol (-) means it'll be private. For functions, you'll see that whatever is to the right of the colon symbol (:) is the return
type of the function. It can also include parentheses, which will show the input parameters for the functions. Some functions don't need
them, so we don't need to place them. Also, note in this case I did add void as the return type for both functions, but that is optional.

# Inheritance

Let's consider the following code:

{% highlight java linenos %}
class FlyingEnemy: public Enemy
{
    public:
        void Fly(void);
    private:
        int flySpeed; 
}
{% endhighlight %}

When an object inherits from another object, it has all of the methods and fields that are contained in the parent class, while also adding their own content and features. In this instance, we have a special FlyingEnemy, which has the ability to fly in addition to all of the functionality of the Enemy class.

In UML, this is normally shown by a solid line with a hollow arrow and looks like the following:

![UML representation of Inheritance]({{ 'images/posts/uml/02.png' | absolute_url }})

# Aggregation

The idea of aggregation is designated by the HAS-A relationship. This is when a single class contains a collection of instances of other classes that are obtained from somewhere else in your program. These are considered to have a weak HAS-A relationship as they can exist outside of the confines of the class.

In this case, I created a new class called CombatEncounter which can have an unlimited number of enemies that can be added to it. However when using aggregation, those enemies will exist before the CombatEncounter starts; and when it finishes, they will also still exist. Through code it would look something like this:

{% highlight java linenos %}
class CombatEncounter
{ 
    public:
        void AddEnemy(Enemy* pEnemy);
    private:
        std::list<Enemy*> enemies;
};
{% endhighlight %}

Inside of UML, it would look like this:

![UML representation of Inheritance]({{ 'images/posts/uml/03.png' | absolute_url }})

# Composition

When using composition, this is a strong HAS-A relationship, and this is when a class contains one or more instances of another class. Unlike aggregation, these instances are not created on their own but, instead, are created in the constructor of the class and then destroyed by its destructor. Put into layman's terms, they can't exist separately from the whole.

In this case, we have created some new properties for the Enemy class, adding in combat skills that it can use, as in the Pokémon series. In this case, for every one enemy, there are four skills that the enemy will be able to have:

{% highlight java linenos %}
class AttackSkill 
{ 
    public:
        void UseAttack(void);
    private:
        int damage;
        float cooldown;
};

class Enemy
{
    public:
        void GetHealth(void) const;
        void SetHealth(int);
    private:
        int         currentHealth;
        int         maxHealth;
        AttackSkill skill1;
        AttackSkill skill2; 
        AttackSkill skill3; 
        AttackSkill skill4; 
};
{% endhighlight %}

The line in the diagram looks similar to aggregation, aside from the fact that the diamond is filled in:

![UML representation of Inheritance]({{ 'images/posts/uml/04.jpg' | absolute_url }})

# References
1. *Extract from: Game Development Patterns and Best Practices,John P. Doran, Matt Casanova, accessed 12 September 2020, <https://amzn.to/3kbafir>.*
2. Software design pattern: https://en.wikipedia.org/wiki/Software_design_pattern