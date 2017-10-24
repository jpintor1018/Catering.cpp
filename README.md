# Catering.cpp







#include <iostream>
using namespace std;
double total_adults (int adults, double Ameal);
double total_children (int child);
double total_dessert (int child, int adults);
double total_foodcosts (double totaladults, double totalchild, double totaldessert);
double tax_tip (double totaladults, double totalchild, double totaldessert, double tax);
double balance (double totaladults, double totalchild, double totaldessert, double roomfee, double totaltax, double deposit);
int main()
{
    int adults, child, dessert;
    double deposit,roomfee, Ameal=12.75, Dcost=1, tax=0.18,Totaladults, TotalChildren,Totaldessert, TotalFoodcosts, Totaltax, x;
    cout<<"Enter number of adults\n";
    cin>>adults;
    cout<<"Enter number of children\n";
    cin>>child;
    cout<<"Enter Deposit\n";
    cin>>deposit;
    cout<<"Enter Room Fee\n";
    cin>>roomfee;
        Totaladults=total_adults (adults,Ameal);
        TotalChildren=total_children(child);
        Totaldessert=total_dessert(child,adults);
        TotalFoodcosts=total_foodcosts(Totaladults, TotalChildren, Totaldessert);
        Totaltax=tax_tip(Totaladults,TotalChildren,Totaldessert,tax);
        x=balance(Totaladults,TotalChildren, Totaldessert,roomfee, Totaltax, deposit);
    cout<<"Number of Adults:                    "<<adults<<endl;
    cout<<"Number of Children:                  "<<child<<endl;
    cout<<"Cost per adult without dessert:      "<<Ameal<<endl;
    cout<<"Cost per children without dessert:   "<<Ameal*.60<<endl;
    cout<<"Cost per dessert:                    "<<Dcost<<endl;
    cout<<"Room fee:                            "<<roomfee<<endl;
    cout<<"Tip and tax rate:                    "<<tax<<endl;
    cout<<endl;
    cout<<endl;
    cout<<"Total cost for adult meals:          "<<Totaladults<<endl;
    cout<<"Total cost for child meals:          "<<TotalChildren<<endl;
    cout<<"Total cost for dessert:              "<<Totaldessert<<endl;
    cout<<"Total food cost:                     "<<TotalFoodcosts<<endl;
    cout<<"Plus tip and tax:                    "<<Totaltax<<endl;
    cout<<"Plus room fee:                       "<<roomfee<<endl;
    cout<<"Less deposit:                        "<<deposit<<endl;
    cout<<"Balance due:                         "<<x<<endl;
    return 0;
}
double total_adults (int adults, double Ameal)
{
    double total;
    total= adults*12.75;
    return total;
}
double total_children (int child)
{
    double total;
    total = child*12.75*.60;
    return total;
}
double total_dessert (int child, int adults)
{
    double total;
    total = child+adults;
    return total;
}
double total_foodcosts (double totaladults, double totalchild, double totaldessert)
{
    double total;
    total = totaladults+totalchild+totaldessert;
    return total;
}
double tax_tip (double totaladults, double totalchild, double totaldessert, double totaltax)
{
    double total;
    total= (totaladults+totalchild+totaldessert)*0.18;
    return total;
}
double balance (double totaladults, double totalchild, double totaldessert, double roomfee, double totaltax, double deposit)
{
    double total;
    total=totaladults+totalchild+totaldessert+totaltax+roomfee-deposit;
    return total;
}

