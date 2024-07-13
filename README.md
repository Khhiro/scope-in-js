# ЧТО ТАКОЕ `Scope in JS`.

![image](https://github.com/user-attachments/assets/2490e5a6-8938-4f3c-90d5-87e0b8451dd0)



Область видимости (или scope) в JS – это как "зона доступа" 🚧 для переменных <br> и функций. Если переменная объявлена <br> глобально 🌍, её видно везде. <br> Локально 🏠 – только внутри функции.



## 3 ипа `scope` js
![image](https://github.com/user-attachments/assets/c45b0d55-8240-4e87-85af-cacfa7f167ae)


<br>

### 1. `Глобальная область видимости` 
— идентификатор доступен во всём тексте программы (во многих языках действует ограничение — только в тексте, находящемся после объявления этого идентификатора).

![](https://cs1.htmlacademy.ru/blog/js/lets-learn-javascript-closures/cf0feb554e54671ea6e5e45120e1bfe3.png)

<br>




### 2. `Локальная область видимости`

— идентификатор доступен только внутри определённой функции (процедуры).

![](https://habrastorage.org/r/w780/webt/pi/x8/xo/pix8xo2liy7a5mpnyaiayj7ybx4.jpeg)


```cs
program Example1;
var 
  a,b,c: Integer; (* Глобальные переменные. *)

  procedure f1;
  var b,c: Integer  (* Локальные переменные процедуры f1. *)
  begin
    a := 10;   (* Изменяет глобальную a. *)
    b := 20;   (* Изменяет локальную b. *)
    c := 30;   (* Изменяет локальную с. *)
    writeln('  4:  ', a, ',', b, ',', c);
  end;

  procedure f2;
  var b,c: Integer (* Локальные переменные процедуры f2. *)
    procedure f21;
    var c: Integer  (* Локальная переменная процедуры f21. *)
    begin
      a := 1000;  (* Изменяет глобальную a. *)
      b := 2000;  (* Изменяет локальную b процедуры f2. *)
      c := 3000;  (* Изменяет локальную c процедуры f21.*)
      writeln('  5:  ', a, ',', b, ',', c);
    end;
  begin
    a := 100; (* Изменяет глобальную a. *)
    b := 200; (* Изменяет локальную b. *)
    c := 300; (* Изменяет локальную c. *)
    writeln('  6:  ', a, ',', b, ',', c);
    f21;
    writeln('  7:  ', a, ',', b, ',', c);
  end;
begin
  (* Инициализация глобальных переменных. *)
  a := 1; 
  b := 2;
  c := 3;
  writeln('  1:  ', a, ',', b, ',', c);
  f1;
  writeln('  2:  ', a, ',', b, ',', c);
  f2;
  writeln('  3:  ', a, ',', b, ',', c);
end.
``` 
<br>

# JavaScript - undefined local

```cs
var scope = "global"; 
function f() {
    alert(scope); // ?
    var scope = "local";
    alert(scope);   
}
```


