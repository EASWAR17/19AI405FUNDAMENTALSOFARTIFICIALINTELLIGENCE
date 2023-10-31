<h1>ExpNo 8 : Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 

<h3>Name: AUGUSTINE J</h3>
<h3>Register Number: 212222240015 </h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<h1>Program: </h1>

```python
wumpus=[["Save","Breeze","PIT","Breeze"],
        ["Smell","Save","Breeze","Save"],
        ["WUMPUS","GOLD","PIT","Breeze"],
        ["Smell","Save","Breeze","PIT"]]
row=0
column=0
arrow=True
player=True
score=0
while(player):
    choice=input("press u to move up\npress d to move down\npress l to move left\npress r to move right\n")
    if choice == "u":
        if row != 0:
            row-=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "d" :
        if row!=3:
            row+=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "l" :
        if column!=0:
            column-=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "r" :
        if column!=3:
            column+=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    else:
        print("move denied")

    if wumpus[row][column]=="Smell" and arrow != False:
        arrow_choice=input("do you want to throw an arrow-->\npress y to throw\npress n to save your arrow\n")
        if arrow_choice == "y":
            arrow_throw=input("press u to throw up\npress d to throw down\npress l to throw left\npress r to throw right\n")
            if arrow_throw == "u":
                if wumpus[row-1][column] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row-1][column] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "d":
                if wumpus[row+1][column] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row+1][column] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "l":
                if wumpus[row][column-1] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row][column-1] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "r":
                if wumpus[row][column+1] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row][column+1] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
                
            
            arrow=False
    if wumpus[row][column] == "WUMPUS" :
        score-=1000
        print("\nWumpus here!!\n You Die\nAnd your score is: ",score
              ,"\n")
        break
    if(wumpus[row][column]=='GOLD'):
        score+=1000
        print("GOLD FOUND!You won....\nYour score is: ",score,"\n")
        break
    if(wumpus[row][column]=='PIT'):
        score-=1000
        print("Ahhhhh!!!!\nYou fell in pit.\nAnd your score is: ",score,"\n")
        break
        
```

<hr>
<h1>Sample Input :</h1>
<hr>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8696111a-a4a7-47cb-ba4b-43a4ef88573f)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/4be5bf06-79fa-4fa0-9334-38a33f06060b)

<h1>Sample Output:</h1>

![278790861-94d45ee4-6005-4ab1-9b58-3dc24ada34c4](https://github.com/Augustine0306/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/119404460/7a80107d-a583-4ff8-91be-6c7792684a43)

<h1>Result:</h1>
Thus, Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic is executed successfully.