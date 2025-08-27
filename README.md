# number-guess-name-
computer vs human in number guessing game
import random
import math

def guess(l,u):
    n=random.randint(l,u)
    # print(n)
    #minium number of steps to achieve the number
    low=l;high=u;steps=0
    while(low<=high):
        mid=low+((high-low)/2)
        if(n==mid):
            # steps=steps+1
            break
        elif(mid>n):
            high=mid-1
            steps=steps+1
        else:
            low=low+1  
            steps=steps+1 
    # print(steps)
    print(f"now, you have only {steps} chance to guess the number--->")
    print("here , the guessing game begins-->")
    c=steps;counter=0
    while(c!=0):
        g=int(input("enter the number:"))
        if(g==n):
            print(f"hey you got the right number its {n}, great job....")
            print(f"you take {counter+1} chances to guess the number")
            print("now you are the winner of the guessing game .")
            print("here, the game ends!!!!!conragulations!!!")
            break
        elif(g>n):
            print("nopes,,you guess higher")
            c=c-1
            print(f"now, you have only {c} chances left....")
            counter+=1
        elif(g<n):
            c=c-1
            if c==0:
                print("sorry!! better luck next time")
                break
            print("nopes,,you guess small")
            print(f"now,,you have only {c} chances")
            counter+=1
        else:
            if g!=int(g):
                print("wrong input enter the interger number between your specified range...")
                counter+=1
    
    
def main():
    upper=int(input("enter the upper bound:"))
    lower=int(input("enter the lower bound:"))
    guess(lower,upper)
    
    
    
if __name__=="__main__":
    main()
    
