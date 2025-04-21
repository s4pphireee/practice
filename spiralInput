#include <iostream>
#include <iomanip>
#include <stdexcept>


void InputSize(int32_t& cols, int32_t& rows) {
    std::cout << "Enter rows and cols values (must be even and equal): ";
    std::cin >> cols >> rows;
    if ((cols <= 0) || (rows <= 0)) {
        throw std::invalid_argument("Invalid argument! Need to be above zero!");
    }
}

void spriralInput(int32_t** &mtr, int32_t size)
{
    int32_t amountOfFillingElem = size - 1;    
    int32_t rows{};    
    int32_t depth{};
    
    while (amountOfFillingElem > 1) {
        
        for (size_t i = depth; i < amountOfFillingElem; ++i) {
            std::cout << "Element in " << rows + 1 << " row and " << i + 1 << " column: ";
            std::cin >> mtr[rows][i];
        }
        
        for (size_t i = depth; i < amountOfFillingElem; ++i) {
            std::cout << "Element in " << i + 1 << " row and " << amountOfFillingElem + 1<< " column: ";
            std::cin >> mtr[i][amountOfFillingElem];
        }
        
        for (size_t i = amountOfFillingElem; i > depth; --i) {
            std::cout << "Element in " << amountOfFillingElem + 1 << " row and " << i + 1 << " column: ";
            std::cin >> mtr[amountOfFillingElem][i];
        }
        
        for (size_t i = amountOfFillingElem; i > depth; --i) {
            std::cout << "Element in " << i + 1 << " row and " << rows + 1 << " column: ";
            std::cin >> mtr[i][rows];
        }
        
        --amountOfFillingElem;
        ++rows;
        ++depth;
    }
    
    int32_t midElement = size / 2;
    std::cout << "Element in " << midElement + 1 << " row and " << midElement + 1 << " column: ";
    std::cin >> mtr[midElement][midElement];
}

void OutputMtr(int32_t** mtr, int32_t cols, int32_t rows) {
    std::cout << "Matrix:" << std::endl;
    for (size_t i = 0; i < rows; ++i) {
        for (size_t j = 0; j< cols; ++j) {
            std::cout << std::setw(4) << mtr[i][j];  
        }
        std::cout << std::endl;  
    }
}

void deleteMtr(int32_t** mtr, int32_t rows){
    for (int i = 0; i < rows; ++i) {
        delete[] mtr[i];  
    }
    delete [] mtr; 
}

int main(){
    
try {
        
    int32_t cols = 0;  
    int32_t rows = 0;         
        
    InputSize(cols, rows);
    
    if (cols != rows) {
        throw std::invalid_argument("Invalid argument! You need to input a square matrix!");
    }
        
    int32_t** mtr = new int32_t*[rows];  
    for (int32_t i = 0; i < rows; ++i) {
        mtr[i] = new int32_t[cols];   
    }
        
    spriralInput(mtr, cols);
    
    OutputMtr(mtr, cols, rows);

    deleteMtr(mtr, cols);
            
    return 0;

    } 
    
    catch (const std::exception& e) {
            std::cerr << "Error: " << e.what() << std::endl;
            return 1;
    }

}




