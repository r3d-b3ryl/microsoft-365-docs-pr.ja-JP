---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Office 365 のメールボックスの回復可能なアイテムフォルダーのサイズを大きくするには、アーカイブメールボックスを有効にして、自動拡張アーカイブをオンにします。 '
ms.openlocfilehash: 37d0e783f3b3a5157fe4a7a9b7d512b09c05d32c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072928"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>保留中のメールボックスの回復可能なアイテムのクォータを拡大する

既定の MRM Policy という名前の既定のアイテム保持ポリシー (Exchange Online の新しいメールボックスに自動的に適用される) には、「回復可能なアイテム」という名前の保持タグが含まれており、14日でアーカイブに移動します。 このアイテム保持タグは、アイテムの 14 日間の保存期間が経過すると、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダーから、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダーへ、アイテムを移動します。 この処理を実行するためには、ユーザーのアーカイブ メールボックスを有効にする必要があります。 アーカイブ メールボックスを有効にしていない場合は、処理が実行されないため、保持中のメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、14 日間の保存期間が経過しても、アーカイブ メールボックスに移動されません。 特に、ユーザーのアーカイブ メールボックスを有効にしないと、保持中のメールボックスから何も削除されないため、[回復可能なアイテム] フォルダーの記憶域クォータを超える可能性があります。 
  
この制限を超える可能性を減らすために、Exchange Online のメールボックスに保留が設定されている場合、回復可能なアイテムフォルダーの記憶域のクォータは自動的に 30 GB から 100 GB に増加します。 アーカイブ メールボックスを有効にした場合は、アーカイブ メールボックスの [回復可能なアイテム] フォルダーの記憶域クォータも、30 GB から 100 GB へ拡大されます。 Exchange Online の自動拡張アーカイブ機能が有効になっている場合、ユーザーのアーカイブ内の回復可能なアイテムフォルダーの記憶域のクォータは無制限になります。
  
  [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。 
  
|**[回復可能なアイテム] フォルダーの場所**|**保持中でないメールボックス**|**保持中のメールボックス**|
|:-----|:-----|:-----|
|プライマリ メールボックス  <br/> |30 GB  <br/> |100 GB  <br/> |
|アーカイブメールボックス<sup>\*</sup> <br/> |無制限  <br/> |無制限  <br/> |
|**[回復可能なアイテム] フォルダーの記憶域クォータの合計** <br/> |無制限  <br/> |無制限  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Exchange Online (Plan 2) ライセンスを持つユーザーの場合、アーカイブメールボックスの初期格納域のクォータは 100 GB です。 ただし、保留中のメールボックスに対して自動拡張アーカイブが有効になっている場合、アーカイブメールボックスと回復可能なアイテムフォルダーの両方の記憶域クォータは 110 GB に増加します。 必要に応じて、アーカイブストレージの容量が無制限にプロビジョニングされます。 自動拡張アーカイブの詳細については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。 
  
保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。
  
- **アーカイブメールボックスを有効にして、自動拡張アーカイブを**有効にする-アーカイブメールボックスを有効にし、Exchange Online の自動拡張アーカイブ機能をオンにして、回復可能なアイテムフォルダーの記憶域の容量を無制限に有効にすることができます。 この結果、プライマリメールボックスの回復可能なアイテムフォルダーでは 110 GB、ユーザーのアーカイブ内の回復可能なアイテムフォルダーの記憶域の容量に制限はありません。 「方法:[セキュリティ & コンプライアンスセンターでアーカイブメールボックスを有効](enable-archive-mailboxes.md)にする」および「 [Office 365 で無制限のアーカイブを有効](enable-unlimited-archiving.md)にする」を参照してください。
    
    > [!NOTE]
    > [回復可能なアイテム] フォルダーの記憶域クォータの上限に近づいているメールボックスのアーカイブを有効にした後、管理フォルダー アシスタントを手動でトリガーしてメールボックスの処理を実行すると、期限切れのアイテムがアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されます。 この手順については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) を参照してください。 ユーザーのメールボックス内のその他のアイテムも新しいアーカイブ メールボックスに移動される可能性があることに注意してください。 アーカイブメールボックスを有効にした後にこれが発生する可能性があることをユーザーに通知することを検討してください。 
  
- メール**ボックスのカスタムアイテム保持ポリシーを作成**する。アーカイブメールボックスとメールボックスの自動拡張アーカイブを訴訟ホールドまたはインプレース保持で有効にすることに加えて、メールボックスの保持時にカスタムアイテム保持ポリシーを作成することもできます。 これにより、ホールドしていないメールボックスに適用される既定の MRM ポリシーとは異なるメールボックスにアイテム保持ポリシーを適用することができます。 これにより、メールボックス専用に設計された保持タグを保持することができます。 これには、回復可能なアイテムフォルダーの新しい保持タグの作成が含まれます。 
    
このトピックの残りの部分では、保持中のメールボックスのカスタム保存ポリシーを作成する手順について説明します。
  
[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[手順 2: 保留中のメールボックスの新しいアイテム保持ポリシーを作成する](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する

最初の手順では、[回復可能なアイテム] フォルダーのカスタム保持タグ (アイテム保持ポリシー タグまたは RPT と呼ばれる) を作成します。 先に説明したように、この RPT により、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダー内のアイテムは、ユーザーのアーカイブ メールボックスの [回復可能なアイテム] フォルダーへ移動されます。 回復可能なアイテムフォルダーの RPT を作成するには、PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 
  
1. [リモート PowerShell で Exchange Online に接続する](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. [回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。  
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    たとえば、次のコマンドを実行すると、[回復可能なアイテム] フォルダー用に "Recoverable Items 30 days for mailboxes on hold" という名前の RPT が作成され、保持期間が 30 日間に設定されます。これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 回復可能なアイテム RPT の保存期間 ( _Agelimitforretention_パラメーターで定義) は、rpt が適用されるメールボックスの削除済みアイテムの保存期間と同じであることをお勧めします。 これによりユーザーは、削除済みアイテムの保持期間全体にわたって、削除済みアイテムがアーカイブ メールボックスに移動される前に、削除済みアイテムを回復することができます。 前の例では、保持期間は、メールボックスの削除済みアイテムの保持期間も 30 日であるという前提を基に、30 日に設定されていました。 Exchange Online メールボックスは、既定では、削除済みアイテムを14日間保持するように構成されています。 ただしこの設定は、最大 30 日にまで変更できます。 詳細については、「 [Exchange Online のメールボックスの削除済みアイテムの保存期間を変更する](https://go.microsoft.com/fwlink/p/?LinkId=286940)」を参照してください。 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>手順 2: 保持中のメールボックスの新しいアイテム保持ポリシーを作成する

次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。  
  
新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。
  
- [Exchange Online の既定のアイテム保持ポリシー](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [アイテム保持ポリシー タグをサポートする既定のフォルダー](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- 「[アイテム保持ポリシーの作成](https://go.microsoft.com/fwlink/p/?LinkId=404422)」の「保持タグを作成する」を参照してください。
    
EAC または Exchange Online の PowerShell を使用して、アイテム保持ポリシーを作成できます。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>EAC を使用してアイテム保持ポリシーを作成する
  
1. EAC で、[**コンプライアンス管理** \> ] [**アイテム保持ポリシー**] の順に移動し](../media/ITPro-EAC-AddIcon.gif)、 **[追加] アイコンをクリック** ![します。
    
2. **[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。  
    
3. [**保持タグ**] で、[追加](../media/ITPro-EAC-AddIcon.gif)] アイコン**をクリックし** ![ます。
    
4. 保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。
    
    ![カスタムの [回復可能なアイテム] 保持タグを選択する](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。
    
6. 保持タグの追加が完了したら、**[OK]** をクリックします。
    
7. **[保存]** をクリックして新しいアイテム保持ポリシーを作成します。 
    
    アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。
    
    ![アイテム保持ポリシーにリンクした保持タグが詳細ウィンドウに表示される](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Exchange Online の PowerShell を使用してアイテム保持ポリシーを作成する
  
保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。  
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

たとえば次のコマンドを実行すると、前の図に示されているアイテム保持ポリシーとそれにリンクされている保持タグが作成されます。
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する

最後のステップでは、手順 2 で作成した新しいアイテム保持ポリシーを、組織内の保持中のメールボックスに適用します。 EAC または Exchange Online の PowerShell を使用して、1つのメールボックスまたは複数のメールボックスにアイテム保持ポリシーを適用することができます。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>EAC を使用して新しい保持ポリシーを適用する
  
1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. リストビューで、アイテム保持ポリシーを適用するメールボックスを選択し、[編集アイコン](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)の**編集** ![] をクリックします。
    
3. **[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。
    
4. **[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。
    
EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。
  
1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。
    
3. 詳細ウィンドウで、**[その他のオプション]** をクリックします。
    
4. **[アイテム保持ポリシー]** 下で **[更新]** をクリックします。
    
5. **[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Exchange Online PowerShell を使用して新しいアイテム保持ポリシーを適用する
  
Exchange Online PowerShell を使用して、単一のメールボックスに新しいアイテム保持ポリシーを適用することができます。 ただし、PowerShell の本当の威力は、これを使用して組織内のすべてのメールボックスを迅速に特定して、訴訟ホールドまたはインプレース保持のいずれかに設定し、保留中のすべてのメールボックスに新しいアイテム保持ポリシーを1つのコマンドで適用できることです。 Exchange PowerShell を使用して1つ以上のメールボックスにアイテム保持ポリシーを適用する例を次に示します。 すべての例で、手順 2 で作成したアイテム保持ポリシーを適用します。
  
この例では、Pilar Pinilla のメールボックスに新しいアイテム保持ポリシーを適用します。
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

この例では、組織内の訴訟ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

この例では、組織内のインプレース ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

**Get-Mailbox** コマンドレットを使用すると、新しいアイテム保持ポリシーが適用されたことを確認できます。 
  
以下は、前の例で実行したコマンドを使用して、"MRM Policy for Mailboxes on Hold" というアイテム保持ポリシーが、訴訟ホールド中のメールボックスとインプレース ホールド中のメールボックスに適用されたことを確認する例です。
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する

保留中のメールボックスに新しいアイテム保持ポリシーを適用した後、管理フォルダーアシスタントが新しいアイテム保持ポリシーの設定を使用してこれらのメールボックスを処理するには、Exchange Online で最大7日かかることがあります。 管理フォルダー アシスタントが実行されるのを待つ代わりに、**Start-ManagedFolderAssistant** コマンドレットを使用して、アシスタントを手動でトリガーし、新しいアイテム保持ポリシーを適用したメールボックスを処理することができます。 
  
Pilar Pinilla のメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

保持中のすべてのメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>詳細情報

- ユーザーのアーカイブ メールボックスを有効にした後は、メールボックスの他のアイテムも ([回復可能なアイテム] フォルダー内のアイテムだけではなく) アーカイブ メールボックスに移動される可能性があることをユーザーに通知することを検討してください。 これは、Exchange Online メールボックスに割り当てられている既定の MRM ポリシーには、アイテムがメールボックスに配信された日から2年後にアーカイブメールボックスにアイテムを移動する保持タグ (既定では、アーカイブに移動する) が含まれているためです。マニュアル. 詳細については、「[既定のアイテム保持ポリシー (Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954) )」を参照してください。
    
- ユーザーのアーカイブ メールボックスを有効にした後は、アーカイブ メールボックス内の [回復可能なアイテム] フォルダーに含まれる削除済みアイテムを回復できることをユーザーに通知することもできます。 Outlook でこの操作を行うには、アーカイブメールボックスの [**削除済みアイテム**] フォルダーを選択し、[**ホーム**] タブの [**サーバーからの削除済みアイテムの回復**] をクリックします。削除済みアイテムの復元の詳細については、「 [Windows 版 Outlook で削除済みアイテムを復元する](https://go.microsoft.com/fwlink/p/?LinkId=624829)」を参照してください。 
