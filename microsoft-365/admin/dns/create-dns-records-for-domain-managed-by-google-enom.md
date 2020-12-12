---
title: Google がドメインを管理している場合に DNS レコードを作成する (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: eNom にアクセスし、Google ドメイン ページから DNS を作成する方法について説明します。
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656857"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Google がドメインを管理している場合に DNS レコードを作成する (eNom)

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
メール アカウントを Microsoft に移行するには、ドメイン レジストラーで DNS レコードを作成する必要があります。
  
**Google Apps for Work** アカウントへのサインアップ時に Google 経由でドメインを購入した場合、DNS レコードは Google が管理し、eNom が登録します。 
  
Google ドメイン ページから eNom にアクセスし、DNS **を作成** できます。 この記事の手順に従ってください。 
  
## <a name="create-the-dns-record"></a>DNS レコードを作成する

1. Google 管理 [コンソールで、[サインイン](https://www.google.com/work/apps/business)] **を選択します**。
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. ドメイン名を入力し、[移動] を **選択します**。
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. ページの下部で、[その他のコントロール] **を選択します**。
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. [ **ドメイン**] を選択します。
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. [ドメイン **] ページで、[** ドメインの追加 **と削除] を選択します**。
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. [ドメイン **] ページで、[DNS** の詳細設定 **] を選択します**。
    
    > [!NOTE]
    > **Google Apps for Work** アカウントへのサインアップ時に Google 経由でドメイン名を購入しなかった場合は、[ **Domains**] ページで [ **Advanced DNS settings**] を使用できません。 代わりに、ユーザーがドメインのホストの Web サイトに直接移動し、DNS 設定にアクセスして、この手順と次の手順に従う必要があります。 詳 [しくは、「G Suite ドメイン設定へのアクセス](https://support.google.com/a/answer/54693?hl=en) 」をご覧ください。 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. [高度 **な DNS 設定] ページで** 、[DNS コンソールに **サインインする] を選択します**。 [ **Sign-in name**] と [ **Password**] の情報をメモします。 次の手順で使用します。 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. [ **Advanced DNS settings**] ページから [ **Sign-in name**] と [ **Password**] を使用して Google **Domain Manager** にログインします。 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. On the **_domain_name_*_ page, in the _* Host Records** section, select **Edit**.
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. [ホスト レコード **] セクションで** 、[新規追加] **を選択します**。
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**ホスト**|**TXT VALUE**|**レコードの種類**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 
  
    [確認する方法](../get-help-with-domains/information-for-dns-records.md)
  
12. **[保存]** を選択します。
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. [変更 **の保存] を選択します**。
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
