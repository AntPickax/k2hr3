---
layout: contents
language: ja
title: TENANT API
short_desc: K2Hdkc based Resource and Roles and policy Rules
lang_opp_file: api_tenant.html
lang_opp_word: To English
prev_url: api_policyja.html
prev_string: POLICY API
top_url: apija.html
top_string: REST API
next_url: api_serviceja.html
next_string: SERVICE API
---

# TENANT API

K2HR3 REST API��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�Ɋ֘A����API�Q�ł��B  

### �⑫
K2HR3 �V�X�e���̃e�i���g�iTENANT�j�́A�A�g����OpenStack�̃e�i���g�i�܂��̓v���W�F�N�g�j�A�������� Kubernetes �� Namespace ���g���܂��B  
K2HR3 REST API�̐ݒ�i�R���t�B�O���[�V�����j�ŁAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�@�\��L���i`localtenants=true`�j�Ƃ����ꍇ�A�Ǝ��̃e�i���g�iTENANT�j���쐬�E�ҏW�E�폜���邱�Ƃ��ł��܂��B  
TENANT API�́AK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�𑀍삷��API�ł��B

## POST�i�V�K�쐬�j
Unscoped User Token�������́AScoped User Token���w�肵�āAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��V�K�쐬���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant

### Header
```
Content-Type: application/json
x-auth-token: U=<Unscoped User Token> or <Scoped User Token>
```

### Request Body
```
{
    tenant:    {
        name:     <tenant name>
        desc:     <description for tenant>
        display:  <display name for tenant>
        users:    [<user name>, ...]
    }
}
```
- name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
- desc  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̐��������L�q���܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓f�t�H���g�̐��������ݒ肳��܂��B  
- display  
K2HR3 Web Application�� ����K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��\���������̕\�������w�肵�܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓e�i���g�iTENANT�j�����ݒ肳��܂��B  
- users  
�쐬���� K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�𗘗p�ł��郆�[�U�iUSER�j����z��Ƃ��Đݒ肵�܂��B  
���̃��N�G�X�g�𑗐M���� (Un)Scoped User Token�Ŏ�����郆�[�U�́A�ȗ��ł��܂��B  
K2HR3�V�X�e���ɓo�^����Ă��郆�[�U�iUSER�j�����w�肷��K�v������܂��B�i[YRN](detail_variousja.html)�t���p�X�ł͂���܂���B�j  
���[�U�iUSER�j�����݂��Ȃ��ꍇ�ɂ́A��������܂��B  

### Response status
201�A40x

### Response Body(JSON)
```
{
    result:     <true/false>
    message:    <null or error message string>
}
```
- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B





## PUT�i�V�K�쐬�j
Unscoped User Token�������́AScoped User Token���w�肵�āAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��V�K�쐬���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant{?name=...}

### Header
```
Content-Type: application/json
x-auth-token: U=<Unscoped User Token> or <Scoped User Token>
```

### URL Arguments
- name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
- desc  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̐��������L�q���܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓f�t�H���g�̐��������ݒ肳��܂��B  
- display  
K2HR3 Web Application�� ����K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��\���������̕\�������w�肵�܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓e�i���g�iTENANT�j�����ݒ肳��܂��B  
- users  
�쐬���� K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�𗘗p�ł��郆�[�U�iUSER�j����z��Ƃ��Đݒ肵�܂��B  
�����w�肷��ꍇ�ɂ́A�z��Ƃ��Ďw�肵�܂��B  
���̃��N�G�X�g�𑗐M���� (Un)Scoped User Token�Ŏ�����郆�[�U�́A�ȗ��ł��܂��B  
K2HR3�V�X�e���ɓo�^����Ă��郆�[�U�iUSER�j�����w�肷��K�v������܂��B�i[YRN](detail_variousja.html)�t���p�X�ł͂���܂���B�j  
���[�U�iUSER�j�����݂��Ȃ��ꍇ�ɂ́A��������܂��B  

### Response status
201�A40x

### Response Body(JSON)
```
{
    result:     <true/false>
    message:    <null or error message string>
}
```
- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B





## POST�i�X�V�j
Unscoped User Token�������́AScoped User Token���w�肵�āAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j���X�V���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant/_tenant name_

- tenant name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
�w�肵��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����݂��Ȃ��ꍇ�͎��s���܂��B  

### Header
```
Content-Type: application/json
x-auth-token: U=<Unscoped User Token> or <Scoped User Token>
```

### Request Body
```
{
    tenant:    {
        id:       <tenant id>
        desc:     <description for tenant>
        display:  <display name for tenant>
        users:    [<user name>, ...]
    }
}
```
- id  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�� _ID_ ���w�肵�܂��B  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j���Ƃ���_ID_����v���Ȃ��ꍇ�A���s���܂��B
- desc  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̐��������L�q���܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓f�t�H���g�̐��������ݒ肳��܂��B  
- display  
K2HR3 Web Application�� ����K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��\���������̕\�������w�肵�܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓e�i���g�iTENANT�j�����ݒ肳��܂��B  
- users  
�쐬���� K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�𗘗p�ł��郆�[�U�iUSER�j����z��Ƃ��Đݒ肵�܂��B  
���̃��N�G�X�g�𑗐M���� (Un)Scoped User Token�Ŏ�����郆�[�U�́A�ȗ��ł��܂��B  
K2HR3�V�X�e���ɓo�^����Ă��郆�[�U�iUSER�j�����w�肷��K�v������܂��B�i[YRN](detail_variousja.html)�t���p�X�ł͂���܂���B�j  
���[�U�iUSER�j�����݂��Ȃ��ꍇ�ɂ́A��������܂��B  

### Response status
201�A40x

### Response Body(JSON)
```
{
    result:     <true/false>
    message:    <null or error message string>
}
```
- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B





## PUT�i�X�V�j
Unscoped User Token�������́AScoped User Token���w�肵�āAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j���X�V���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant/_tenant name_{?id=...}

- tenant name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
�w�肵��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����݂��Ȃ��ꍇ�͎��s���܂��B  

### Header
```
Content-Type: application/json
x-auth-token: U=<Unscoped User Token> or <Scoped User Token>
```

### URL Arguments
- id  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�� _ID_ ���w�肵�܂��B  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j���Ƃ���_ID_����v���Ȃ��ꍇ�A���s���܂��B
- desc  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̐��������L�q���܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓f�t�H���g�̐��������ݒ肳��܂��B  
- display  
K2HR3 Web Application�� ����K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��\���������̕\�������w�肵�܂��B  
���̒l�͏ȗ��\�ł���A�ȗ����ꂽ�ꍇ�̓e�i���g�iTENANT�j�����ݒ肳��܂��B  
- users  
�쐬���� K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�𗘗p�ł��郆�[�U�iUSER�j����z��Ƃ��Đݒ肵�܂��B  
�����w�肷��ꍇ�ɂ́A�z��Ƃ��Ďw�肵�܂��B  
���̃��N�G�X�g�𑗐M���� (Un)Scoped User Token�Ŏ�����郆�[�U�́A�ȗ��ł��܂��B  
K2HR3�V�X�e���ɓo�^����Ă��郆�[�U�iUSER�j�����w�肷��K�v������܂��B�i[YRN](detail_variousja.html)�t���p�X�ł͂���܂���B�j  
���[�U�iUSER�j�����݂��Ȃ��ꍇ�ɂ́A��������܂��B  

### Response status
201�A40x

### Response Body(JSON)
```
{
    result:     <true/false>
    message:    <null or error message string>
}
```
- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B




## GET�i���X�g�j
Unscoped User Token�������́AScoped User Token���w�肵�āAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̃��X�g���擾���܂��B  
�擾����e�i���g�iTENANT�j�̃��X�g�́A���[�U�iUSER�j�����p��������Ă���e�i���g�iTENANT�j�݂̂ł��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant{?expand=true/false}

### Header
```
Content-Type: application/json
x-auth-token: U=<Scoped User Token>
```

### URL argument
- expand=_true or false_
�擾����e�i���g�iTENANT�j�̃��X�g��W�J���邩�ۂ����w�肵�܂��B  
�W�J����ꍇ�́A_true_���w�肵�܂��B  

### Response status
200�A40x

### Response Body(JSON) 
- �W�J����ꍇ�iexpand=true�j  
```
{
    result:           <true/false>
    message:          <null or error message string>
    tenants: [
        {
             name:    <tenant name>,
             id:      <tenant id>,
             desc:    <description for tenant>,
             display: <display name for tenant>,
             user:    [user, ...]
         },
         ...
    ]
}
```
- �W�J���Ȃ��ꍇ�iexpand=false�j  
```
{
    result:   <true/false>
    message:  <null or error message string>
    tenants:  [<tenant name>, ...]
}
```

- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B
- tenants  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̔z��ł��B  
�W�J����ꍇ�i`expand=true`�j�́A�e�i���g�iTENANT�j�̏���z��ŕԂ��܂��B  
�W�J���Ȃ��ꍇ�i`expand=false`�j�́A�e�i���g�iTENANT�j����z��ŕԂ��܂��B  
- tenants[*]:name  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�����ݒ肳��܂��B
- tenants[*]:id  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j��_ID_���ݒ肳��܂��B
- tenants[*]:desc  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̐��������ݒ肳��܂��B
- tenants[*]:display  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̕\�������ݒ肳��܂��B
- tenants[*]:user  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̗��p��������Ă��郆�[�U�iUSER�j���̃��X�g��z��ŕԂ��܂��B





## GET�i�e�i���g�w��j
Unscoped User Token�������́AScoped User Token���w�肵�AK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̏����擾���܂��B  
���[�U�iUSER�j�����p��������Ă��Ȃ��e�i���g�iTENANT�j���w�肵���ꍇ�A���s���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant/_tenant name_

- tenant name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
�w�肵��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����݂��Ȃ��ꍇ�͎��s���܂��B  

### Header
```
Content-Type: application/json
x-auth-token: U=<Scoped User Token>
```

### Response status
200�A40x

### Response Body(JSON) 
```
{
    result:        <true/false>
    message:       <null or error message string>
    tenant: {
        name:      <tenant name>,
        id:        <tenant id>,
        desc:      <description for tenant>,
        display:   <display name for tenant>,
        user:      [user, ...]
    }
}
```
- result  
API�̏������ʂ�true/false�ŕԂ��܂��B
- message  
�������ʂ�false�i���s�j�̂Ƃ��ɁA�G���[���b�Z�[�W���i�[����܂��B
- tenant:name  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�����ݒ肳��܂��B
- tenant:id  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j��_ID_���ݒ肳��܂��B
- tenant:desc  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̐��������ݒ肳��܂��B
- tenant:display  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̕\�������ݒ肳��܂��B
- tenant:user  
�W�J����ꍇ�iexpand=true�j�ɕԂ����e�i���g�iTENANT�j���Ɋ܂܂��v�f�ŁA�e�i���g�iTENANT�j�̗��p��������Ă��郆�[�U�iUSER�j���̃��X�g��z��ŕԂ��܂��B



## HEAD
Unscoped User Token�������́AScoped User Token���w�肵�AK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̑��݂��m�F���܂��B  
���[�U�iUSER�j�����p��������Ă��Ȃ��e�i���g�iTENANT�j���w�肵���ꍇ�A���s���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant/_tenant name_

- tenant name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
�w�肵��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����݂��Ȃ��ꍇ�͎��s���܂��B  

### Header
```
Content-Type: application/json
x-auth-token: U=<Scoped User Token>
```

### Response status
204�A40x

### Response Body(JSON)
�Ȃ�



## DELETE
Unscoped User Token�������́AScoped User Token���w�肵�A���[�U�iUSER�j�� K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̗��p�s�ɂ��܂��B  
���̏������s�������ʁAK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�̗��p�ł��郆�[�U�iUSER�j�����Ȃ��Ȃ����ꍇ�AK2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�͍폜����܂��B  
���[�U�iUSER�j�����p��������Ă��Ȃ��e�i���g�iTENANT�j���w�肵���ꍇ�A���s���܂��B  

#### ����
���ׂĂ�TENANT API�ɂ́AUnscoped User Token�������́AScoped User Token���K�v�ł��B  
Scoped User Token���w�肳�ꂽ�ꍇ�A���̃g�[�N���������e�i���g�͖�������AUnscoped User Token�Ɠ��l�Ƀ��[�U���݂̂��g�p���܂��B  

### Endpoint(URL)
http(s)://_API SERVER:PORT_/v1/tenant/_tenant name_{?id=<tenant id>}

- tenant name  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����w�肵�܂��B  
���̒l�� `local@` �v���t�B�b�N�X���t�^����Ă��Ȃ��ꍇ�A�����I�� `local@` �v���t�B�b�N�X���t�^���ꂽ�e�i���g�iTENANT�j���ɕύX����܂��B  
�w�肵��K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j�����݂��Ȃ��ꍇ�͎��s���܂��B  

### Header
```
Content-Type: application/json
x-auth-token: U=<Scoped User Token>
```

### URL argument
- id  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j��_ID_���w�肵�܂��B  
K2HR3�N���X�^�[���[�J���e�i���g�iTENANT�j���Ƃ���_ID_����v���Ȃ��ꍇ�A���s���܂��B

### Response status
204�A40x

### Response Body(JSON)
�Ȃ�
