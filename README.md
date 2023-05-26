# KN-M9

## Forward Euler

```
function y_Euler(x0, y0, b, h:real):real;
   {menghitung nilai y(b) pada PDB
   y'=f(x,y); y(x0)=y0
   dengan metode Euler
   }
var
  r, n: integer;
  x, y: real;
begin
  n:=(b-x0)/h; {jumlah langkah}
  y:=y0; {nilai awal}
  x:=x0;
  for r:=1 to n do 
   begin
    y:=y + h*f(x,y); { hitung solusi y[xr] }
    x:=x + h; { hitung titik berikutnya }
   end; {for}
  y_Euler:=y; {y(b)}
end;
```

## Runge-Kutta Orde 4

```
function y_RK4(x0, y0, b, h:real):real;
  {menghitung y(b) dengan metode Runge-Kutta orde empat pada PDB
  y'=f(x,y); y(x0)=y0 }
var
  r, n: integer;
  x, y, k1, k2, k3, k4: real;
begin
  n:=(b - x0)/h; {jumlah langkah}
  y:=y0; {nilai awal}
  x:=x0;
  for r:=1 to n do
   begin 
    k1:=h*f(x, y);
    k2:=h*f(x + h/2, y + k1/2);
    k3:=h*f(x + h/2, y + k2/2);
    k4:=h*f(x + h, y + k3);
    y:=y + (k1 + 2*k2 + 2*k3 + k4)/6 { nilai y(xr) }
    x:=x+h; { titik berikutnya}
   end;
  y_RK4:=y;
end; 
```
