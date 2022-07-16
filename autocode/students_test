package coverage

import (
	"os"
	"strconv"
	"testing"
	"time"

	"github.com/stretchr/testify/assert"
)

// DO NOT EDIT THIS FUNCTION
func init() {
	content, err := os.ReadFile("students_test.go")
	if err != nil {
		panic(err)
	}
	err = os.WriteFile("autocode/students_test", content, 0644)
	if err != nil {
		panic(err)
	}
}

// WRITE YOUR CODE BELOW

func TestLenStudents(t *testing.T) {
	var testPpl = People{
		Person{"Artem","Vetkin", time.Now()},
	}
	assert.Equal(t, testPpl.Len(), len(testPpl), "Count of pepople shoul be equal")

}

func TestLessStudents(t *testing.T) {
	var testPpl = People{
		Person{"Artem","Vetkin", time.Now().Local()},
		Person{"Artem","Vetkin", time.Now().Local()},
		Person{"Artyom","Vetkin", time.Now().Local()},
		Person{"Detkin","Petkin", time.Now().Local().Add(time.Hour * time.Duration(3))},
	}

	assert.Equal(t, testPpl.Less(0, 1), false, "First person should be less then second")
	assert.Equal(t, testPpl.Less(1, 2), true, "First person should be less then second")
	assert.Equal(t, testPpl.Less(0, 3), false, "First person should be less then second")
}

func TestSwapStudents(t *testing.T) {
	testPpl := People{
		Person{"Artem","Vetkin", time.Now().Local()},
		Person{"Artem","Vetkin", time.Now().Local()},
		Person{"Artyom","Vetkin", time.Now().Local()},
		Person{"Detkin","Petkin", time.Now().Local().Add(time.Hour * time.Duration(3))},
	}

	firstPerson := testPpl[1]
	secondPerson := testPpl[2]
	testPpl.Swap(1,2)
	assert.Equal(t, testPpl[1], secondPerson)
	assert.Equal(t, testPpl[2], firstPerson)
		
}

func TestMatrixInit(t *testing.T) {
	testMatrix, _ := New(
		`1 2 3 4 5
		5 4 3 2 1
		4 4 4 4 4`)
	assert.Equal(t, testMatrix, &Matrix{
		3,5, []int{1, 2, 3, 4, 5, 5, 4, 3, 2, 1, 4, 4, 4, 4, 4},
	})
}

func TestMatrixWithWrongCols(t *testing.T) {
	_, err := New(
		`1 2 3 4 5
		5 4 3 2
		4 4 4 4 4`)
	assert.Equal(t, err.Error(), "Rows need to be the same length")
}

func TestMatrix(t *testing.T) {
	_, err := New(
		`1 f 3 4 5
		5 4 3 2
		4 4 4 4 4`)
	assert.ErrorIs(t, err, strconv.ErrSyntax)
}

func TestMatrixRowsMethod(t *testing.T) {
	testMatrix, _ := New(
		`1 2 3 4 5
		5 4 3 2 1
		4 4 4 4 4`)
	expected := [][]int([][]int{{1, 2, 3, 4, 5}, {5, 4, 3, 2, 1}, {4, 4, 4, 4, 4}})
	assert.Equal(t, testMatrix.Rows(), expected)
}

func TestMatrixColsMethod(t *testing.T) {
	testMatrix, _ := New(
		`1 2 3 4 5
		5 4 3 2 1
		4 4 4 4 4`)
	expected := [][]int{{1, 5, 4}, {2, 4, 4}, {3, 3, 4}, {4, 2, 4}, {5, 1, 4}}
	assert.Equal(t, testMatrix.Cols(), expected)
}

func TestMatrixSetMethod(t *testing.T) {
	testMatrix, _ := New(
		`1 2 3 4 5
		5 4 3 2 1
		4 4 4 4 4`)

	expectedRow := 1
	expectedCol := 1
	expectedValue := 3
	testMatrix.Set(expectedRow,expectedCol,expectedValue)
	gettedValue := testMatrix.data[expectedRow*testMatrix.cols+expectedCol]
	assert.Equal(t, gettedValue, expectedValue)
}

func TestMatrixSetMethodBadData(t *testing.T) {
	testMatrix, _ := New(
		`1 2 3 4 5
		5 4 3 2 1
		4 4 4 4 4`)

	expectedRow := 5
	expectedCol := 5
	expectedValue := 3
	isInserted := testMatrix.Set(expectedRow,expectedCol,expectedValue)
	assert.Equal(t, isInserted, false)
}