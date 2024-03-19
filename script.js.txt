// script.js
function calculateAge() {
  const dob = new Date(document.getElementById('dob').value);
  const today = new Date();
  const age = today.getFullYear() - dob.getFullYear();
  document.getElementById('age').innerHTML = age+" Years Old";
}
document.getElementById('dob').addEventListener('change', calculateAge);
// for getting states wr country
function populateStates() {
  const country = document.getElementById('country').value;
  const stateDropdown = document.getElementById('state');

  // Clear previous options
  stateDropdown.innerHTML = '<option value="">Select State</option>';

  document.getElementById('city').innerHTML='<option value="">Select City</option>';

  // Define indianStates variable outside the if-else blocks
  let indianStates = [];

  // Populate states based on the selected country
  if (country === "India") {
    indianStates = ["Andhra Pradesh", "Tamil Nadu", "Telangana", "Kerala"];
  } else if (country === "USA") {
    indianStates = ["Texas", "California", "Florida"];
  } else if (country === "Japan") {
    indianStates = ["Hokkaido", "Fukui", "Gunma"];
  }

  // Populate the dropdown options with the states
  indianStates.forEach(state => {
    const option = document.createElement('option');
    option.value = state;
    option.textContent = state;
    stateDropdown.appendChild(option);
  });
}
function populateCities() {
  const state = document.getElementById('state').value;
  const cityDropdown = document.getElementById('city');
  cityDropdown.innerHTML = '<option value="">Select City</option>';
  let cities = [];
  if (state === "Andhra Pradesh") {
    cities = ["Visakhapatnam", "Vijayawada", "Guntur"];
  } else if (state === "Tamil Nadu") {
    cities = ["Chennai", "Coimbatore", "Madurai"];
  } else if (state === "Telangana") {
    cities = ["Hyderabad", "Warangal", "Karimnagar"];
  } else if (state === "Kerala") {
    cities = ["Thiruvananthapuram", "Kochi", "Kozhikode"];
  } else if (state === "Texas") {
    cities = ["Houston", "Austin", "Dallas"];
  } else if (state === "California") {
    cities = ["Los Angeles", "San Francisco", "San Diego"];
  } else if (state === "Florida") {
    cities = ["Miami", "Orlando", "Tampa"];
  } else if (state === "Hokkaido") {
    cities = ["Sapporo", "Hakodate", "Asahikawa"];
  } else if (state === "Fukui") {
    cities = ["Fukui City", "Obama", "Tsuruga"];
  } else if (state === "Gunma") {
    cities = ["Maebashi", "Takasaki", "Kiryu"];
  }
  cities.forEach(city => {
    const option = document.createElement('option');
    option.value = city;
    option.textContent = city;
    cityDropdown.appendChild(option);
  });
}
function validatePhoneNumber(phoneNumber) {
  return /^\d{10}$/.test(phoneNumber);
}

function validateEmail(email) {
  return email.includes('@') && email.split('@')[1].includes('.');
}

document.getElementById("btn").addEventListener("click", () => {
  const email = document.getElementById("email").value;
  const phoneNumber = document.getElementById("phoneNumber").value;

  const isEmailValid = validateEmail(email);
  const isPhoneNumberValid = validatePhoneNumber(phoneNumber);
  if(! isPhoneNumberValid) alert("enter proper phone number");
if(! isEmailValid) alert("enter proper email");

});





