# Files For News Banner Component

****

1. <mark style="color:green;">**composition.tsx**</mark>

* finds component corresponding to incoming json and takes the data and returns an object with the desired format.

1. **data.js**

* Dummy Data

<details>

<summary><mark style="color:green; ">data.js</mark></summary>

```js
export const Data = {
    fields: {
        'Icon Path': {
            value: {
                src: 'https://scdev13.duke-energy.com/_/media/images/flipboard/flipboard-electric-vehicle.jpg',
                alt: 'Image Alt Text',
            },
        },
        Rounded: {
            value: true,
        },
        Title: {
            value: 'Here to help during this difficult time.',
        },
        Body: {
            value: 'Customers who need additional time to pay any outstanding balance may qualify for financial assistance. Learn how we are taking action to help in response to COVID-19.',
        },
        'BG Color': {
            fields: {
                Value: {
                    value: 'bg-teal-lighter',
                },
                Setting: {
                    value: 'Teal',
                },
            },
        },
        'CTA URL': {
            value: {
                href: '/test/newsbanner/cta',
                target: '_self',
                text: 'View Resources',
            },
        },
    },
};
```

</details>

1. <mark style="color:green;">**index.tsx**</mark>

* Main Component

1. <mark style="color:green;">**stories.js**</mark>
2. <mark style="color:green;">**test.tsx**</mark>
3. <mark style="color:green;">**types.ts**</mark>
