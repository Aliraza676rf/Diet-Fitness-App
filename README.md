function signUp() {
    let email = document.getElementById("email").value;
    let password = document.getElementById("password").value;

    auth.createUserWithEmailAndPassword(email, password)
    .then((userCredential) => {
        document.getElementById("login-message").innerText = "Signup Successful!";
    })
    .catch((error) => {
        document.getElementById("login-message").innerText = error.message;
    });
}

function login() {
    let email = document.getElementById("email").value;
    let password = document.getElementById("password").value;

    auth.signInWithEmailAndPassword(email, password)
    .then((userCredential) => {
        document.getElementById("login-message").innerText = "Login Successful!";
    })
    .catch((error) => {
        document.getElementById("login-message").innerText = error.message;
    });
}

function googleSignIn() {
    let provider = new firebase.auth.GoogleAuthProvider();
    auth.signInWithPopup(provider)
    .then((result) => {
        document.getElementById("login-message").innerText = "Google Login Successful!";
    })
    .catch((error) => {
        document.getElementById("login-message").innerText = error.message;
    });
}
