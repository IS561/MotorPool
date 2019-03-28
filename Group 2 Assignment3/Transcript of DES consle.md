### Step1: consult the console
Warning: Y>=50 may raise a computing exception if non-ground at run-time.
Warning: Next rule is unsafe because of variable: [Y]
gt50(Y) :-
Y>=50.
Warning: Y<500 may raise a computing exception if non-ground at run-time.
Warning: Next rule is unsafe because of variable: [Y]
st500(Y) :-
Y<500.
Warning: Y<50 may raise a computing exception if non-ground at run-time.
Warning: Next rule is unsafe because of variable: [Y]
st50(Y) :-
Y<50.
![image](https://user-images.githubusercontent.com/46877258/55187739-cb8ce280-5167-11e9-8124-61be90b22bc8.png){:height="50%" width="50%"}
***
### Step2: check provostApprove, deanApprove and isSelfSupporting
DES> provostApprove(kbea) 
{
  provostApprove(kbea)
}
Info: 1 tuple computed.

DES> deanApprove(kbea) 
{
  deanApprove(kbea)
}
Info: 1 tuple computed. 

DES> isSelfSupporting(kbea) 
{
  isSelfSupporting(kbea)
}
Info: 1 tuple computed.
![image](https://user-images.githubusercontent.com/46877258/55187981-40f8b300-5168-11e9-8904-be35cafe64e1.png)
***
