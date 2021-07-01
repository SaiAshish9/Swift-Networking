# Useful third party dependency

```
Alamofire (can be installed using cocoapods or swiftUIPackages)
```

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
```
EmergencyCallHandler doesn' care about what delegate is associated with . It can be class , struct or subclass.
```

```
UTF-8 is the standardized protocol to encode text
```

# Closures

```
import UIKit

func calculator(n1:Int,n2:Int)->Int{
  return n1 * n2
}

calculator(n1:2,n2:3)

=>

func calculator(n1:Int,n2:Int,operation:(Int,Int)->Int) -> Int {
   return operator(n1,n2)
}

func add(no1:int,no2:Int)->Int {
   return no1 + no2
}

calculator(n1:2,n2:3,operator:add)

=>

let result = calculator(n1:2,n2:3){$0*$1}

import UI

let array= [6,2,3,9,4,1]
func addOne(n1:Int)->Int{ return n1+1 }
array.map(addOne)
array.map({(n1,n2)->Int in return n!+1})
array.map{$0+1}
array.map{"\($0)"}
```
# Conversion to closure

```
highlight and press enter
```

# Code formatting

```
cmd + I
```

# Type alias & protocols (JSON encoding & decoding)

```
:Decodable :Encodable :Codable
```

# External parameter names

``
func a(x y :Int){print(y)}  func a(x:2){}
func a(_ y:Int){print(y)} func a(2){}
``

# Markers

```
//MARK:
```

# DispatchQueue

```
let task = URLSession.shared.dataTask(with:url){
(data,response,error) if let data = data {
 self.label.text = "\(data.count)"
}
}
task.resume()
```

# Extensions

```
var x=3.1234
x.round()

extension Double{
  func round(to places: Int){
  let p = pow(10,places)
  var n = self
  n= n * p
  n.round()
  n/=p
  return n
  }
}


extension WeatherViewController: WeatherManagerDelegate
extension WeatherViewController: CLLocationManagerDelegate

OR class WeatherViewController: UIViewController, WeatherManagerDelegate,CLLocationManagerDelegate

```
