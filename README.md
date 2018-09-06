#include <iostream>
#include <iomanip>
void displayArray(short *arr,size_t arraySize){
        for ( size_t i = 0; i < arraySize; ++i ) {
                std::cout << std::setw ( 4 ) << arr [ i ];
        } // for i
        std::cout<<"\n";
}
void bubbleSort(short *arr,size_t arraySize){
        for ( size_t pass = 0; pass < arraySize; ++pass ) {
                std::cout<<"\nPass : "<<(pass+1)<<" \n";
                for ( size_t j = 0; j < arraySize-1-pass; ++j ) {  //change in loop
                        if ( arr [ j ] > arr [ j + 1 ] ) {
                            std::cout<<"swapping "<<arr[j]<<" and  "<<arr[j+1]<<" \n";
                                short hold;
                                hold = arr [ j ];
                                arr [ j ] = arr [ j + 1 ];
                                arr [ j + 1 ] = hold;
                        } // if
                } // for ji
                std::cout<<"Array :";
                displayArray(arr,arraySize);
        } // for pass
}

int main() {
        const short arraySize = 10;
        short arr [ arraySize ] = { 2,6, 4, 8, 10, 12, 89, 68, 45, 37 };
        std::cout << "Data items in original order:" << std::endl;
        displayArray(arr,arraySize);
        bubbleSort(arr,arraySize);
        std::cout << std::endl << "Data items in ascending order:" << std::endl;
        displayArray(arr,arraySize);
        std::cout << std::endl;
        return 0;
}
