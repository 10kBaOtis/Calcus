const display = document.getElementById("display");

function appendToDisplay(value) {
    display.value += value;
}

function clearDisplay() {
    display.value = "";
}

function deleteLast() {
    display.value = display.value.slice(0, -1);
}

function calculate() {
    try {
        let expression = display.value;

let result = eval(expression);

display.value = result;

addHistory(expression + " = " + result);
    } catch {
        display.value = "Error";
    }
}
const darkButton = document.getElementById("darkMode");

darkButton.onclick = function(){
    document.body.classList.toggle("dark");
};
function addHistory(operation){

    let historyList = document.getElementById("historyList");

    let item = document.createElement("li");

    item.textContent = operation;

    historyList.appendChild(item);

}
