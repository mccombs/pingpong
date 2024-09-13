<template>
    <div>
        <h1>Home</h1>
    </div>
</template>

<script lang="js" defer>
let referrer = document?.referrer;
let location = window?.location;
let userAgent = navigator?.userAgent;

let person = {
    referrer: referrer,
    host: location?.host,
    pathname: location?.pathname,
    ua: userAgent,
};

await fetch("https://api.ipify.org?format=json").then((res) => {
    res.json().then((data) => {
        person.ip = data.ip;
    });
});

console.log(person);
</script>
