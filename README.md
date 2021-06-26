# High Quality Images

```
portable network graphics gets pixelated when zoomed in
vector images doesn't get pixalated
e.g. -> .pdf

check preserve vector data at inspector window of Assests.xcassets
```

# Useful textfield properties

```
ReturnKey -> Go 
autoCapitalize : true (london -> London)
secureKey : true *******

textFieldShouldReturn
textFieldDidBeginEditing
textFieldShouldbeginEditing
textFieldDidEndEditing
textFieldShouldEndEditing
```

# Swift protocols

```
protocol config(){
  canFly()
}

class A:config{ func canFly(){} }

class B:A,config{  override func canFly(){}  }

struct C:canFly{}
```

# Delegate design pattern

```
protocol AdvancedLifeSupport(){
   func performCPR()
}

class EmergencyCallHandler{
  var delegate:AdvancedLifeSupport?
  func assessSituation(){printf("Can you tell me what happened?")}
  func medicalEmergency(){ delegate?.performCPR() }  
}

struct Paramedic:AdvancedLifeSupport{

init(handler: EmergencyCallHandler){
   handler.delegate = self
}

func performCPR(){
  print("T")
}
}
let emilio = EmergencyCallback()
let p = Paramedic(handler : emilio)
emilio.assessSituation()

class Doctor: AdvancedLifeSupport{
   init(handler: EmergencyCallHandler){
     handler.delegate = self
   }
   func performCPR(){
     print("")
   }
}
class Surgeon:Doctor {
   override performCPR(){
     super.performCPR()
     print("")
   }
}
}

```
