---
layout: blog
thumbnail: ./thumbnail.jpg
title: ការ host website របស់យើងនៅក្នុង hosting service
description: យើងបានឃើញហើយថាការ host website ប្រើប្រាស់ Github គឺមានផលវិបាកសម្រាប់ការ host website ដែលមាន build step ដូចជា React, Vue, ... ដែលត្រូវឲ្យមានការ generate static files សិនដើម្បីអោយមានការ host នៅលើ Github បាន។ ដូច្នេះយើងអាចប្រើប្រាស់ hosting service សម្រាប់ front-end ដូចជា vercel ឬ netlify។
---

> 📝 ចំណាំ ការ host website នៅលើ vercel និង netlify នេះគឺមានភាពងាយស្រួលជាងការ host នៅលើ hosting service ធម្មតា ដោយយើងមិនចាំបាច់ config ច្រើនដែល vercel និង netlify មានមកស្រាប់។

## ការសម្រេចចិត្ត

នៅក្នុងនេះយើងនឹងប្រើប្រាស់ vercel សម្រាប់ការ host website។ នៅក្នុងនេះមាន៖

- ការប្រើប្រាស់ Github សម្រាប់ការរក្សាទុក code
- ការប្រើប្រាស់ vercel interface និង github action ដើម្បី host website

## ការរៀបចំ

មុននឹងយើង host website បាន យើងអាច upload ឬ push code ចូលទៅក្នុង Github ជាមុនសិន ដើម្យីឲ្យយើង connect ទៅ vercel បាន។

### រប្រៀបក្នុងការ upload ឬ push code

មុននឹងធ្វើការ upload ឬ push code ចូលទៅក្នុង [Github](https://github.com) យើងត្រូវការ Login ឬ Sign up មុនសិន។

![](https://imgur.com/frZdSmm.png)

> គ្រាន់តែចូលទៅកាន់ homepage របស់ Github ហើយយើង click ទៅលើ `New`

![](https://imgur.com/HE0Xzt2.png)

> បំពេញ information នៃ repository ហើយ click ទៅលើ `Create repository`

![](https://imgur.com/qcZmfkI.png)

> យើងអាច follow instruction របស់ Github តាមរយៈអ្វីយើងដែលត្រូវការ

![](https://imgur.com/dKLdadL.png)

## ប្រើប្រាស់ vercel website ដើម្បី host website

មុននឹងធ្វើការ import project ចូលទៅក្នុង [vercel](https://vercel.com) យើងត្រូវការ Login ឬ Sign up មុនសិន។ បើសិនជាយើងប្រើប្រាស់ Github គឺមានភាពងាយស្រួលក្នុងការ import។

![](https://imgur.com/5OKdO21.png)
![](https://imgur.com/IIiQQMb.png)

> Click ទៅលើ `Add New...` ហើយ click ទៅលើ `Project`

![](https://imgur.com/rD69poA.png)

> Click ទៅលើ `import` ដែលជា project យើងចង់ import

![](https://imgur.com/IDplZtw.png)

> បំពេញ information ទៅលើ vercel project និង select ទៅលើ framework preset បើសិន vercel select ខុសឬមិនបាន select

![](https://imgur.com/jYFhgvo.png)

> បើសិនជាមាន custom configuration យើងអាចបំពេញ information នៅកន្លែងនេះបាន

![](https://imgur.com/2dw7K6T.png)
![](https://imgur.com/y3Z9E1G.png)

> បន្ទាប់ពីជោគជ័យយើងអាចឃើញ project របស់យើងនៅលើ vercel homepage

![](https://imgur.com/MnUr70k.png)

> បើសិនជាទៅ homepage អាច click ទៅលើ project ឬ click ទៅលើ `Continue to Dashboard`

![](https://imgur.com/QZQfIL9.png)

> បានឃើញ status ready មានន័យថាការ deploy របស់យើងបានជោគជ័យ ហើយយើងអាច click ទៅលើ link របស់ domain ដែល vercel បាន generate ឲ្យដើម្បីឆែកមើល website ដែលបាន deploy នោះ

![](https://imgur.com/KibMmMu.png)
![](https://imgur.com/4UKSMmm.png)
![](https://imgur.com/oY9da7O.png)

> Click ទៅលើ `Settings` ហើយ click ទៅលើ `Domains` ជាកន្លែងដើម្បី setup custom domain បាន

![](https://imgur.com/7KFcXkO.png)

> នៅក្នុង `Settings` យើងអាច click ទៅលើ `Environment Variables` គឺយើងអាច setup `.env` file របស់យើងនៅទីនេះបាន

![](https://imgur.com/oRh0RFw.png)

> នៅក្នុង `Settings` យើងអាច click ទៅលើ `General` ហើយ scroll ចុះមកក្រោមយើងនឹងឃើញកន្លែង delete project បើសិនចង់លុបគ្រាន់តែ click ទៅលើ `Delete`

> ⚠️ ការលុប project ចេញពី vercel គឺមិនអាច restore មកវិញបានទេ

![](https://imgur.com/naDH9CW.png)

> បំពេញ information ដែល vercel ត្រូវការ

![](https://imgur.com/YVQIQrB.png)

> Project ត្រូវបានលុប

## ការប្រើប្រាស់ Github Action ដើម្បី host website

នៅក្នុងការប្រើប្រាស់ Github Action នេះគឺយើងនឹងប្រើប្រាស់ [amondnet/vercel-action](https://github.com/amondnet/vercel-action) ដើម្បី deploy website របស់យើង។

### ការរៀបចំ

មុននឹងយើងអាចប្រើប្រាស់ Github Action ដើម្បី auto hosting website យើងត្រូវការ [vercel cli](https://vercel.com/docs/cli) នៅពេលដែលយើងបានទាញយកមកដាក់លើ PC យើងហើយយើងអាចប្រើប្រាស់ command របស់ vercel នៅក្នុង Terminal ឬ Command Propt បានតាមរយៈ `vercel --version` បើសិនឃើញ output មកបែបនេះ `ខាងក្រោម` មានន័យថាយើងទាញយករួចរាល់ហើយ។

```bash
Vercel CLI :version
:version
```

> 📝 ចំណាំ កន្លែង :version មានន័យថាជា version របស់ vercel ដែលយើងបានទាញមក ដូចនៅលើ PC ដែលយកទៅអនុវត្ត គឺមាន output បែបនេះ
>
> ```bash
> Vercel CLI 28.18.4
> 28.18.4
> ```

ហើយបន្ទាប់ពីការ run command vercel បានជោគជ័យ យើងត្រូវភ្ជាប់ vercel cli របស់យើងជាមួយ vercel account យើងជាមុនសិនតាមរយៈការ run command `vercel login` យើងគ្រាន់តែជ្រើសរើស method ណាដែលយើងបាន login ជាមួយ vercel។

> ⚠️ បើសិនមាន បញ្ហាជាមួយ vercel cli អត់បើក browser ឲ្យយើង យើងអាចចុចទៅលើ link ដែលមាននៅលើ console ហើយយកទៅបើកនៅក្នុង browser ណាដែលយើងបាន login ជាមួយ vercel

### ការប្រើប្រាស់

នៅពេលដែលយើងបានដំឡើង vercel cli រួចរាល់យើងអាច run command `vercel` នៅក្នុង project directory របស់យើង ឬ តាមរយៈ `vercel path/to/project` (បើសិនយើង run command `vercel` នៅក្នុង project directory មានភាពងាយស្រួលជាង)។ បន្ទាប់មក vercel cli នឹងធ្វើការ generate directory មួយហៅថា `.vercel` ដែលនៅក្នុងនោះមាន JSON file មួយដែលមាន information សម្រាប់ឲ្យយើង connect ទៅ project & team ដែល vercel cli បានបង្កើតឲ្យយើងនៅពេលដែលយើង run command `vercel` ឬ `vercel path/to/project`។

> បើចង់ស្វែងយល់បន្ថែមអាចមើល `README.txt` file នៅក្នុង directory `.vercel`។ នៅពេលដែល vercel cli បង្កើត directory `.vercel` ឲ្យយើង យើងនឹងបានឃើញ directory `.vercel` ត្រូវបានដាក់ចូលទៅក្នុង `.gitignore` file របស់យើងដែលកុំឲ្យមានការច្រលំ push ចូល Github ដោយចៃដន្យ

![](https://imgur.com/f42ZKpP.png)

នៅពេលដែលយើងទទួលបាន `project.json` file យើងចូលទៅក្នុង [Github Repo](https://github.com) របស់យើង ហើយ setup environment តាមរយៈ

![](https://imgur.com/Iq8hUCi.png)

> ចូលទៅក្នុង Settings Tab

![](https://imgur.com/vRnCkIz.png)

> បើក `Screats and variables` ហើយ click ទៅលើ `Actions` រួច click ទៅលើ `New repository secret`

![](https://imgur.com/9tVzS7r.png)
![](https://imgur.com/vfb5UcD.png)

> បន្ទាប់មក add បញ្ចូល ដែលមានសភាពបែបនេះ ORG*ID គឺមានតម្លៃចាប់ផ្តើមដោយ `team*`និង PROJECT_ID គឺមានតម្លៃចាប់ផ្តើមដោយ`prj\_`

បន្ទាប់ពីការ setup project រួចគឺយើងត្រូវការ vercel token ដោយចូលទៅកាន់ [vercel](https://vercel.com)

![](https://imgur.com/ylRZVcG.png)

> Click ទៅលើ profile របស់យើងបន្ទាប់មក click ទៅលើ `Account Settings`

![](https://imgur.com/9dAm9ok.png)

> Click ទៅលើ `Token` បន្ទាប់មកយើងត្រូវបំពេញ ឈ្មោះ, scope និង ការផុតកំណត់ ដូចដែលអ្វីដែលបានបំពេញនៅក្នុងរូបភាពខាងលើ

> ⚠️ ការដាក់ ការផុតកំណត់មិនមានថ្ងៃផុតកំណត់បែបនេះគឺមានភាពងាយស្រួលមិនចាំបាច់ update vercel token នៅក្នុង Github Repo របស់យើង។ ជាការល្អយើងប្រើប្រាស់ token មួយសម្រាប់ website មួយបានហើយ ជៀសវាងការប្រើដូចគ្នានាំឲ្យមានភាពប៉ះពាល់ នៅពេលដែលយើង revoke token ណាមួយ

![](https://imgur.com/8hXMkjH.png)

> Copy ទៅលើ token នោះ

![](https://imgur.com/qI0cI3p.png)

> យកទៅដាក់ដូច setup vercel នៅលើ Github Repo ដែរ

យើងអាចបង្កើត Github action បានហើយតាមរយៈ បង្កើត file មួយនៅក្នុង `.github` directory និង `workflows` directory ដែលជាប្រភេទ `yml` file ដូចដែលបានឧទាហរណ៍

![](https://imgur.com/EoWEP6o.png)

> 📝 ខ្វះ timeout-minutes

```yml
# path: .github/workflows/vercel.yml

# vercel-merge.yml
name: Deploy to vercel on merge
on:
  push:
    branches:
      - main
jobs:
  build_and_deploy:
    permissions: write-all
    runs-on: ubuntu-latest
    timeout-minutes: 30
    steps:
      - uses: actions/checkout@v2
      - uses: amondnet/vercel-action@v20
        with:
          vercel-token: ${{ secrets.VERCEL_TOKEN }}
          vercel-org-id: ${{ secrets.ORG_ID}}
          vercel-project-id: ${{ secrets.PROJECT_ID}}
          vercel-args: "--prod"
```

នៅក្នុង Github action របស់យើងមានដូចជា៖

**name**: ឈ្មោះសំដៅទៅលើ action មួយនោះ
**on**: លក្ខខណ្ឌនៅពេលណាដែល action របស់យើងដំណើរការ ដោយនៅក្នុងនេះគឺមានការដើរនៅពេលដែលយើងបាន push code ចូលទៅក្នុង main branch
**jobs**: ការងារណាខ្លះដែលយើងនឹងដាក់ឲ្យ run
**build-and-deploy**: ឈ្មោះរបស់ការងារនោះដែលយើងអាចដាក់ឈ្មោះអ្វីក៏បានដែល
**permissions**: ការដាក់ការអនុញ្ញាតឲ្យទៅ action មួយនោះ
**runs-on**: ដំណើរការនៅលើ machine អ្វី
**timeout-minutes**: ដាក់ timeout នៅពេលដែល action run មិនឈប់
**steps**: ការដាក់ដំណើរការពីណាទៅណា គឺគិតពីលើចុះក្រោម
**uses**: បើទៅលើ action ដោយដាក់ឈ្មោះឲ្យ
**with**: នៅពេលខ្លះ action ត្រូវការ arguments ដើម្បីបំពេញការងារ

បើសិនជាចង់ឆែកមើល information ពី action អាចចូលទៅតាម link ខាងក្រោមបាន៖

- [actions/checkout](https://github.com/actions/checkout) @v2
- [amondnet/vercel-action](https://github.com/amondnet/vercel-action) @v20

នៅពេលដែលយើងមានការ setup រួចរាល់ យើងអាច push code ចូលទៅក្នុង github repo យើងនោះ action នឹងធ្វើការដោយស្វ័យប្រវត្តិ ដែលយើងអាចមើលឃើញនៅ

![](https://imgur.com/abP39BH.png)

> Click ទៅលើ `Actions` ដើម្បីមើល actions របស់ repository ទាំងអស់

![](https://imgur.com/beaCrIp.png)

នៅពេលដែលយើង push code ចូលបើសិន github actions របស់យើង setup ត្រូវគឺមានសភាពបែបនេះដែលវាកំពុង process។

![](https://imgur.com/Byh4oPL.png)

> នៅពេលដែល action របស់យើង run ដោយជោគជ័យ គឺមាន ✅

![](https://imgur.com/EqubI3g.png)

> អាចចូលទៅឆែកមើលនៅក្នុង vercel បាន

## ដោះស្រាយបញ្ហា ឬ Troubleshooting

### Action មានការ run និងឈប់ត្រឹម re-authenticate

ដោយយើងមិនបាច់មានការ fix ក៏ website យើងនៅ host ជាធម្មតា ប៉ុន្តែបើសិនចង់ fix គឺអាចឆែកចូលមើលតាមរយៈ [#138](https://github.com/amondnet/vercel-action/issues/138)។

បើសិន vercel action run អត់បានអស់នោះ ការដាក់ custom domain (alias domain) ក៏មិនបានដាក់ដែរ
