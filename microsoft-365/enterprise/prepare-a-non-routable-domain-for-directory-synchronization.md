---
title: ディレクトリ同期のために非ルーティング ドメインの準備を整える
ms.author: kvice
author: kelleyvice-msft
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
description: 展開できないドメインがオンプレミスのユーザー アカウントに関連付けられている場合の操作を、テナントと同期する前にMicrosoft 365します。
ms.openlocfilehash: cecaee814d19f78b973ebd2f06c8d2c665d905de
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356914"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>ディレクトリ同期のために非ルーティング ドメインの準備を整える

オンプレミス のディレクトリを Microsoft 365 と同期する場合は、Azure Active Directory (Azure AD) に確認済みドメインを持っている必要があります。 オンプレミスの Active Directory ドメイン サービス (DS) ドメインに関連付けられているユーザー プリンシパル名 (UPN) AD同期されます。 ただし、.local など、アウトできないドメインを含む UPN (例: billa@contoso.local) は、.onmicrosoft.com ドメイン (例: billa@contoso.onmicrosoft.com) に同期されます。 

現在、AD DS のユーザー アカウントに .local" ドメインを使用している場合は、Microsoft 365 ドメインと適切に同期するために、billa@contoso.com などの検証済みドメインを使用するドメインを変更してください。
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>オンプレミスドメインが .local の場合は、どうしますか?

Azure AD ConnectをADテナントの Azure ADテナントに同期Microsoft 365します。 詳細については、「オンプレミス ID と Azure ID の統合」を[参照AD。](/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connectユーザーの UPN とパスワードを同期して、ユーザーがオンプレミスで使用するのと同じ資格情報でサインインできます。 ただし、Azure AD Connectは、ユーザーによって検証されるドメインにのみ同期Microsoft 365。 つまり、ドメインは Azure ADによってAD、Microsoft 365によって管理AD。 つまり、ドメインは有効なインターネット ドメイン (.com、.org、.net、.us など) である必要があります。 内部の AD DS で使用されているドメインが、ラウトできないドメイン (".local"など) のみを使用している場合は、Microsoft 365 テナントの検証済みドメインと一致する可能性があります。 この問題を解決するには、オンプレミスのドメイン DS でプライマリ ドメインAD、または 1 つ以上の UPN サフィックスを追加します。
  
### <a name="change-your-primary-domain"></a>プライマリ ドメインを変更する

プライマリ ドメインを、たとえば、Microsoft 365で確認したドメインに contoso.com。 その後、ドメイン contoso.local を持つすべてのユーザーが、contoso.com。 ただし、これは非常に複雑なプロセスであり、より簡単なソリューションについては、次のセクションで説明します。
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>UPN サフィックスを追加してユーザーを更新する

"ローカル" の問題を解決するには、AD DS に新しい UPN サフィックスまたはサフィックスを登録して、Microsoft 365 で確認したドメイン (またはドメイン) と一致します。 新しいサフィックスを登録した後、ユーザー の UPN を更新して、ユーザー アカウントが新しいドメイン名に置き換 billa@contoso.com。
  
確認済みドメインを使用するために UPN を更新した後、オンプレミスの DS と ADを同期Microsoft 365。
  
#### <a name="step-1-add-the-new-upn-suffix"></a>手順 1: 新しい UPN サフィックスを追加する**
  
1. DS ドメイン ADで、[ツール] [Active Directoryドメインと信頼] \> **を選択します**。
    
    **または (Windows Server 2012 を所有していない場合)**
    
    **Windows キー + R** を押して **[実行]** ダイアログ開き、「Domain.msc」と入力してから **[OK]** を選択します。
    
    ![[Active Directory ドメインと信頼関係] を選択します。](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. [Active **Directory ドメインと信頼]** ウィンドウで **、[Active Directory ドメイン** と信頼] を右クリックし、[プロパティ] を **選択します**。
    
    ![[Active Directory ドメインと信頼] を右クリックし、[プロパティ] を選択します。](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. **[UPN サフィックス]** タブの **[代替の UPN サフィックス]** ボックスに、新しいサフィックスを入力して **[追加]** \> **[適用]** を選択します。
    
    ![新しい UPN サフィックスを追加します](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    サフィックスの追加が完了したら、**[OK]** を選択します。 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>手順 2: 既存のユーザーの UPN サフィックスを変更する
  
1. DS ドメイン コントローラー ADサーバー マネージャーで、[ツール]  [Active Directory ユーザーとコンピューター] \> **を選択します**。
    
    **または (Windows Server 2012 を所有していない場合)**
    
    **Windows キー + R** を押して **[実行]** ダイアログ開き、「Dsa.msc」と入力してから **[OK]** を選択します。
    
2. ユーザーを選択し、右クリックして **[プロパティ]** を選択します。
    
3. **[アカウント]** タブの UPN サフィックス ドロップダウン リストで、新しい UPN サフィックスを選択してから **[OK]** をクリックします。
    
    ![ユーザーの新しい UPN サフィックスを追加する](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. すべてのユーザに対して、ここまでの手順を実行します。
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>PowerShell を使用してすべてのユーザーの UPN サフィックスを変更する

更新するユーザー アカウントが多い場合は、PowerShell を使用する方が簡単です。 次の例では [、Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) と [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) コマンドレットを使用して、すべての contoso.local サフィックスを DS 内の contoso.com にADします。 

たとえば、次の PowerShell コマンドを実行して、すべての contoso.local サフィックスを次のコマンドに更新 contoso.com。
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

[詳細については、「Active Directory Windows PowerShell モジュール」](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10))を参照して、DS でのWindows PowerShellをADしてください。