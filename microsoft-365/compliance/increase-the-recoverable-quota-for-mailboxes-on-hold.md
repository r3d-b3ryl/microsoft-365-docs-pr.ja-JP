---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: アーカイブ メールボックスを有効にし、自動拡張アーカイブを有効にして、Microsoft 365内のメールボックスの回復可能なアイテム フォルダーのサイズを増やします。
ms.openlocfilehash: bbeb72c6a055be42e06c450afccb35965d149dce
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66015018"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>保留中のメールボックスの回復可能なアイテムのクォータを拡大する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

既定のExchangeアイテム保持ポリシー (*既定の MRM ポリシー*) は、Exchange Onlineの新しいメールボックスに自動的に適用され、アーカイブに 14 日間移動する回復可能なアイテムという名前の保持タグが含まれています。 このアイテム保持タグは、アイテムの 14 日間の保存期間が経過すると、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダーから、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダーへ、アイテムを移動します。 この処理を実行するためには、ユーザーのアーカイブ メールボックスを有効にする必要があります。 アーカイブ メールボックスを有効にしていない場合は、処理が実行されないため、保持中のメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、14 日間の保存期間が経過しても、アーカイブ メールボックスに移動されません。 特に、ユーザーのアーカイブ メールボックスを有効にしないと、保持中のメールボックスから何も削除されないため、[回復可能なアイテム] フォルダーの記憶域クォータを超える可能性があります。

この制限を超える可能性を減らすために、回復可能なアイテム フォルダーのストレージ クォータは、Exchange Online内のメールボックスに保留が配置されると、30 GB から 100 GB に自動的に増やされます。 アーカイブ メールボックスを有効にした場合は、アーカイブ メールボックスの [回復可能なアイテム] フォルダーの記憶域クォータも、30 GB から 100 GB へ拡大されます。 Exchange Onlineの自動拡張アーカイブ機能が有効になっている場合、回復可能なアイテム フォルダーを含むユーザーのアーカイブ メールボックスの合計ストレージ クォータは 1.5 TB です。

  [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。

| [回復可能なアイテム] フォルダーの場所 | 保持中でないメールボックス | 保持中のメールボックス |
|:-----|:-----|:-----|
|プライマリ メールボックス |30 GB |100 GB |
|回復可能なアイテム フォルダーを含むアーカイブ メールボックス <sup>\*</sup> |1.5 TB |1.5 TB |

> [!NOTE]
> <sup>\*</sup>アーカイブ メールボックスの初期ストレージ クォータは、Exchange Online (プラン 2) ライセンスを持つユーザーに対して 100 GB です。 ただし、保留中のメールボックスに対して自動拡張アーカイブを有効にすると、アーカイブ メールボックスと回復可能なアイテム フォルダーの両方のストレージ クォータが 110 GB に増やされます。 必要に応じて、最大 1.5 TB のアーカイブ ストレージ領域 (回復可能なアイテム フォルダーを含む) がプロビジョニングされます。 自動拡張アーカイブの詳細については、「 [自動展開アーカイブの詳細](autoexpanding-archiving.md)」を参照してください。

保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。

- **アーカイブ メールボックスを有効にし、自動展開アーカイブを有効にします。** アーカイブ メールボックスを有効にし、Exchange Onlineで自動拡張アーカイブ機能を有効にするだけで、回復可能なアイテム フォルダーの追加のストレージ容量を有効にすることができます。 これにより、プライマリ メールボックスの回復可能なアイテム フォルダーには 110 GB、アーカイブフォルダーと回復可能なアイテム フォルダーの合計ストレージ容量は最大 1.5 TB になります。 詳細については、「 [アーカイブ メールボックスを有効にする](enable-archive-mailboxes.md) 」と「 [自動展開アーカイブを有効にする」を参照](enable-autoexpanding-archiving.md)してください。

    > [!NOTE]
    > 回復可能なアイテム フォルダーのストレージ クォータを超えそうなメールボックスのアーカイブを有効にした後、管理フォルダー アシスタントを実行して、有効期限が切れたアイテムがアーカイブ メールボックスの回復可能なアイテム フォルダーに移動されるように、手動でアシスタントをトリガーしてメールボックスを処理することができます。 この手順については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) を参照してください。 ユーザーのメールボックス内のその他のアイテムも新しいアーカイブ メールボックスに移動される可能性があることに注意してください。 アーカイブ メールボックスを有効にした後に、これが発生する可能性があることをユーザーに伝えるのを検討してください。

- **保留中のメールボックスのカスタム Exchangeアイテム保持ポリシーを作成します。** 訴訟ホールドまたはIn-Placeホールドのメールボックスに対してアーカイブ メールボックスを有効にし、アーカイブを自動拡張するだけでなく、メールボックスの保持に関するカスタム Exchangeアイテム保持ポリシーを作成することもできます。 これにより、保留状態でないメールボックスに適用される既定の MRM ポリシーとは異なる保留メールボックスにアイテム保持ポリシーを適用し、保留メールボックス用に設計された保持タグを適用できます。 これには、回復可能なアイテム フォルダーの新しい保持タグの作成が含まれます。

このトピックの残りの部分では、保留中のメールボックスのカスタム Exchangeアイテム保持ポリシーを作成する手順について説明します。

[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[手順 2: 保留中のメールボックスの新しいExchangeアイテム保持ポリシーを作成する](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[手順 3: 新しいExchangeアイテム保持ポリシーを保留中のメールボックスに適用する](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する

最初の手順では、[回復可能なアイテム] フォルダーのカスタム保持タグ (アイテム保持ポリシー タグまたは RPT と呼ばれる) を作成します。 先に説明したように、この RPT により、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダー内のアイテムは、ユーザーのアーカイブ メールボックスの [回復可能なアイテム] フォルダーへ移動されます。 回復可能なアイテム フォルダーの RPT を作成するには、PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。

1. [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

2. [回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。 

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    たとえば、次のコマンドでは、"回復可能なアイテムの 30 日間のメールボックスを保持" という名前の回復可能なアイテム フォルダーの RPT を作成し、保持期間は 30 日間です。 これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 回復可能なアイテム RPT の保持期間 (  _AgeLimitForRetention_ パラメーターで定義) は、RPT が適用されるメールボックスの削除済みアイテムの保持期間と同じであることをお勧めします。 これによりユーザーは、削除済みアイテムの保持期間全体にわたって、削除済みアイテムがアーカイブ メールボックスに移動される前に、削除済みアイテムを回復することができます。 前の例では、保持期間は、メールボックスの削除済みアイテムの保持期間も 30 日であるという前提を基に、30 日に設定されていました。 Exchange Online メールボックスは、既定で削除されたアイテムを 14 日間保持するように構成されています。 ただしこの設定は、最大 30 日にまで変更できます。 詳細については、「[Exchange Online内のメールボックスの削除済みアイテムの保持期間を変更](https://www.microsoft.com/?ref=go)する」を参照してください。

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>手順 2: 保留中のメールボックスの新しいExchangeアイテム保持ポリシーを作成する

次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。 

新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。

- [Exchange Online の既定のアイテム保持ポリシー](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [アイテム保持ポリシー タグをサポートする既定のフォルダー](/exchange/security-and-compliance/messaging-records-management/default-folders)

- アイテム保持ポリシーの作成に関するトピックの「 [アイテム保持タグの作成](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) 」セクション。

EAC または Exchange Online PowerShell を使用してアイテム保持ポリシーを作成できます。

### <a name="use-the-eac-to-create-a-retention-policy"></a>EAC を使用してアイテム保持ポリシーを作成する

1. EAC で、**コンプライアンス管理** \> **の保持ポリシー** に移動し、[**追加**![アイコン] をクリックします](../media/ITPro-EAC-AddIcon.gif)。

2. **[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。 

3. [**保持タグ**] で、[**追加**![アイコン] をクリックします](../media/ITPro-EAC-AddIcon.gif)。

4. 保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。

    ![カスタムの回復可能なアイテム保持タグを選択します。](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。

6. 保持タグの追加が完了したら、**[OK]** をクリックします。

7. **[保存]** をクリックして新しいアイテム保持ポリシーを作成します。

    アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。

    ![アイテム保持ポリシーにリンクされたアイテム保持タグが詳細ウィンドウに表示されます。](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Exchange Online PowerShell を使用してアイテム保持ポリシーを作成する

保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。 

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>
```

たとえば、次のコマンドは、前の図に表示されているアイテム保持ポリシーとリンクされた保持タグを作成します。

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>手順 3: 新しいExchangeアイテム保持ポリシーを保留中のメールボックスに適用する

最後のステップでは、手順 2 で作成した新しいアイテム保持ポリシーを、組織内の保持中のメールボックスに適用します。 EAC または Exchange Online PowerShell を使用して、アイテム保持ポリシーを 1 つのメールボックスまたは複数のメールボックスに適用できます。

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>EAC を使用して新しい保持ポリシーを適用する

1. **[受信者メールボックス]** >  に移動 **します**。

2. リスト ビューで、アイテム保持ポリシーを適用するメールボックスを選択し、[ **編集]** ![アイコンをクリックします](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。

3. **[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。

4. **[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。

EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。

1. **[受信者メールボックス]** >  に移動 **します**。

2. リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。

3. 詳細ウィンドウで、**[その他のオプション]** をクリックします。

4. 
            **[アイテム保持ポリシー]** 下で **[更新]** をクリックします。

5. **[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。 

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>PowerShell Exchange Online使用して新しいアイテム保持ポリシーを適用する

PowerShell Exchange Onlineを使用して、1 つのメールボックスに新しいアイテム保持ポリシーを適用できます。 ただし、PowerShell の本当の機能は、それを使用して、訴訟ホールドまたはIn-Placeホールドのいずれかになっている組織内のすべてのメールボックスをすばやく識別し、1 つのコマンドで保留されているすべてのメールボックスに新しいアイテム保持ポリシーを適用できるということです。 Exchange PowerShell を使用して 1 つ以上のメールボックスにアイテム保持ポリシーを適用する例を次に示します。 すべての例で、手順 2 で作成したアイテム保持ポリシーを適用します。

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

新しいExchangeアイテム保持ポリシーを保留中のメールボックスに適用した後、管理フォルダー アシスタントが新しいアイテム保持ポリシーの設定を使用してこれらのメールボックスを処理するには、Exchange Onlineで最大 7 日間かかる場合があります。 管理フォルダー アシスタントが実行されるのを待つ代わりに、**Start-ManagedFolderAssistant** コマンドレットを使用して、アシスタントを手動でトリガーし、新しいアイテム保持ポリシーを適用したメールボックスを処理することができます。

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

- ユーザーのアーカイブ メールボックスを有効にした後は、メールボックスの他のアイテムも ([回復可能なアイテム] フォルダー内のアイテムだけではなく) アーカイブ メールボックスに移動される可能性があることをユーザーに通知することを検討してください。 これは、Exchange Online メールボックスに割り当てられている既定の MRM ポリシーには、アイテムがメールボックスに配信された日またはユーザーが作成した 2 年後にアイテムをアーカイブ メールボックスに移動する保持タグ (既定の 2 年間のアーカイブへの移行という名前) が含まれているためです。 詳細については、「[Exchange Onlineの既定のアイテム保持ポリシー」](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)を参照してください。

- ユーザーのアーカイブ メールボックスを有効にした後は、アーカイブ メールボックス内の [回復可能なアイテム] フォルダーに含まれる削除済みアイテムを回復できることをユーザーに通知することもできます。 アーカイブ メールボックスの **[削除済みアイテム**] フォルダーを選択し、[**ホーム**] タブの [**サーバーから削除済みアイテムの回復**] をクリックすると、Outlookでこれを行うことができます。削除済みアイテムの回復の詳細については、「[WindowsのOutlookで削除されたアイテムを回復する」を](https://go.microsoft.com/fwlink/p/?LinkId=624829)参照してください。
