#include <iostream>
using namespace std;
int a ;
int b ;
int c ;
int d ;
int e ;
int f ;
int g ;
int z ;//代表坦克总数
int t ;//代表总时间
 
​void buy1() {
​​a = a + 1;
​​b = b + 1;
​​c = c + 1;
​​d = d + 1;
​​z = z + 1;
​​t = t + 1;
​​
​
​}
​void buy2() {
​​a = a + 1;
​​b = b + 1;
​​c = c + 1;
​​d = d + 1;
​​e = e + 1;
​​z = z + 1;
​​t = t + 2;
​​
 
​}
​void buy3() {
​​b = b + 1;
​​c = c + 1;
​​d = d + 1;
​​f = f + 1;
​​z = z + 1;
​​t = t + 4;
​​
​}
​void buy4() {
​​a = a + 1;
​​b = b + 1;
​​c = c + 1;
​​d = d + 1;
​​g = g + 1;
​​z = z + 1;
​​t = t + 6;
​​
​}
 
int​F(int v) {
​
​if (v< 600) {
​​return v;
​}
​if (v >=600 && v< 1600) {
​​buy1();
​​v = v - 500;
​​if (v >= 1000) {
​​​buy2();
​​​return F(v - 800);
​​}
​​else {
​​​return F(v );
​​}
 
​}
​if (v >= 1600 && v < 2800) {
​​buy1();
​​buy2();
​​v = v - 1300;
​​if (v >=1200) {
​​​buy3();
​​​return F(v - 800);
​​}
​​else {
​​return F(v );
​}
 
​}
​if (v >= 2800 && v < 4550) {
​​buy1();
​​buy2();
​​buy3();
​​v = v - 2100;
​​if (v >= 1750) {
​​​buy4();
​​​return F(v - 1150);
​​}
​​else {
​​​return F(v);
​​}
​}
​else {
​​buy1();
​​buy2();
​​buy3();
​​buy4();
​​return F(v-3250);
​}
}
int main()
{
​int m;
​cin >> m;
​
​F(m);
​cout << z << endl;
​cout << t << endl;
​cout << a << " "<<b <<" " << c <<" " << d <<" " << e <<" "<< f <<" "<< g << endl;
 
​return 0;
 
 
}
