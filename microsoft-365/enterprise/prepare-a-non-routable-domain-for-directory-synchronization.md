---
title: ディレクトリ同期のために非ルーティング ドメインの準備を整える
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Microsoft 365 テナントと同期する前に、オンプレミスのユーザー アカウントに関連付けられているアウトできないドメインがある場合の操作について説明します。
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780334"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>ディレクトリ同期のために非ルーティング ドメインの準備を整える

オンプレミス ディレクトリを Microsoft 365 と同期する場合は、Azure Active Directory (Azure AD) に確認済みドメインが必要です。 オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインに関連付けられているユーザー プリンシパル名 (UPN) だけが同期されます。 ただし、".local" など、アウトできないドメインを含む UPN (例: billa@contoso.local) は 、.onmicrosoft.com ドメイン (例: billa@contoso.onmicrosoft.com) に同期されます。 

現在、AD DS のユーザー アカウントに ".local" ドメインを使用している場合は、Microsoft 365 ドメインと正しく同期するために、billa@contoso.com などの確認済みドメインを使用するドメインに変更をお勧めします。
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>".local" オンプレミス ドメインのみがある場合は、

Azure AD Connect を使用して、AD DS を Microsoft 365 テナントの Azure AD テナントに同期します。 詳細については、「オンプレミス ID と Azure AD」 [を参照してください](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)。
  
Azure AD Connect は、ユーザーの UPN とパスワードを同期し、ユーザーがオンプレミスで使用するのと同じ資格情報でサインインできます。 ただし、Azure AD Connect は、Microsoft 365 によって検証されたドメインにのみユーザーを同期します。 つまり、Microsoft 365 ID は Azure ADによって管理されるので、ドメインは Azure AD。 つまり、ドメインは有効なインターネット ドメイン (.com、.org、.net、.us など) である必要があります。 内部 AD DS が、アウトできないドメイン (".local" など) のみを使用している場合、これは Microsoft 365 テナントの確認済みドメインと一致する可能性があります。 この問題を解決するには、オンプレミスの AD DS でプライマリ ドメインを変更するか、1 つ以上の UPN サフィックスを追加します。
  
### <a name="change-your-primary-domain"></a>プライマリ ドメインを変更する

プライマリ ドメインを、Microsoft 365 で確認したドメインに変更します (たとえば、contoso.com。 その後、ドメイン contoso.local を持つすべてのユーザーが更新され、contoso.com。 ただし、これは非常に複雑なプロセスであり、次のセクションでは簡単なソリューションについて説明します。
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>UPN サフィックスを追加してユーザーを更新する

".local" の問題を解決するには、Microsoft 365 で確認したドメインに一致する新しい UPN サフィックスまたはサフィックスを AD DS に登録します。 新しいサフィックスを登録した後、".local" を新しいドメイン名に置き換えるユーザー UPN を更新します。たとえば、ユーザー アカウントが次のように表示billa@contoso.com。
  
確認済みドメインを使用するために UPN を更新した後、オンプレミスの AD DS を Microsoft 365 と同期する準備が整います。
  
#### <a name="step-1-add-the-new-upn-suffix"></a>手順 1: 新しい UPN サフィックスを追加する**
  
1. DS ドメイン ADサーバー マネージャーで **、[Tools** \> **Active Directory Domains and Trusts] を選択します**。
    
    **または (Windows Server 2012 を所有していない場合)**
    
    **Windows キー + R** を押して **[実行]** ダイアログ開き、「Domain.msc」と入力してから **[OK]** を選択します。
    
    ![[Active Directory ドメインと信頼関係] を選択します。](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts,** and then choose **Properties**.
    
    ![[Active Directory のドメインと信頼] を右クリックし、[プロパティ] を選択します。](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. **[UPN サフィックス]** タブの **[代替の UPN サフィックス]** ボックスに、新しいサフィックスを入力して **[追加]** \> **[適用]** を選択します。
    
    ![新しい UPN サフィックスを追加します](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    サフィックスの追加が完了したら、**[OK]** を選択します。 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>手順 2: 既存のユーザーの UPN サフィックスを変更する
  
1. DS ドメイン コントローラー ADサーバー マネージャーで **、[Tools** \> **Active Directory Users and Computers] を選択します**。
    
    **または (Windows Server 2012 を所有していない場合)**
    
    **Windows キー + R** を押して **[実行]** ダイアログ開き、「Dsa.msc」と入力してから **[OK]** を選択します。
    
2. ユーザーを選択し、右クリックして **[プロパティ]** を選択します。
    
3. **[アカウント]** タブの UPN サフィックス ドロップダウン リストで、新しい UPN サフィックスを選択してから **[OK]** をクリックします。
    
    ![ユーザーの新しい UPN サフィックスを追加する](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. すべてのユーザに対して、ここまでの手順を実行します。
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>PowerShell を使用してすべてのユーザーの UPN サフィックスを変更する

更新するユーザー アカウントが多い場合は、PowerShell を使用する方が簡単です。 次の例では [、Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) および [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) コマンドレットを使用して、すべての contoso.local サフィックスを contoso.com DS 内ADします。 

たとえば、次の PowerShell コマンドを実行して、すべての contoso.local サフィックスを次のコマンドにcontoso.com。
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

この [DS での Windows PowerShellの](https://go.microsoft.com/fwlink/p/?LinkId=624314) 使用の詳細については、Active Directory Windows PowerShell モジュールADしてください。 

