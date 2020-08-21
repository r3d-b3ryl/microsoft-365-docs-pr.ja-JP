---
title: 事前設定されたセキュリティ ポリシー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) および Office 365 Advanced Threat Protection (ATP) の保護機能に対して標準および制限のポリシー設定を適用する方法について学習できます。
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825259"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>EOP と Office 365 ATP での事前セキュリティ ポリシー

事前設定済みのセキュリティ ポリシーは、推奨されるすべてのスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用するための一元的な場所を提供します。 ポリシー設定は構成できません。 むしろ、ユーザーが作業を中断することなく、ユーザーから問題のあるコンテンツを切り分けずにバランスアップするために、Microsoft によって設定され、データセンター内の観測とエクスペリエンスに基づいています。

このトピックの残りの部分では、事前に設定されたセキュリティ ポリシーと、その構成方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>作成される事前設定のセキュリティ ポリシー

事前設定済みのセキュリティ ポリシーは、次の要素で構成されます。

- プロファイル
- ポリシー
- ポリシー設定

さらに、複数の事前に設定されたセキュリティ ポリシーとその他のポリシーが同じ人物に適用される場合は、優先順位が重要になります。

### <a name="profiles-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのプロファイル

プロファイルは保護レベルを決定します。 使用可能なプロファイルは次のとおりです。

- **標準的**な保護: ほとんどのユーザーに適したベースライン保護プロファイルです。
- **高い保護:** 選択されたユーザーに対してより、より総した保護プロファイル (高いターゲット、または優先ユーザー)。

プロファイルが適用される対象ユーザーと適用対象でないユーザーを決定する条件と例外をルールに使用します。

各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

使用できる条件と例外は以下のとおりです。

- **受信者は、** 組織内のメールボックス、メール ユーザー、メール連絡先です。
- **受信者は組織内の**: グループのメンバーです。
- **受信者のドメインは、Microsoft**365 で構成されている承認済みドメインです。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーは、EOP および 365 ATP のさまざまな保護機能からの対応Officeを使用します。 これらのポリシーは、標準_保護または_制限付き**のセキュリティ ポリシー****をユーザーに割り**当てた後に作成されます。 これらのポリシーは変更できません。

- **Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを使用している Microsoft 365 組織と Exchange Online メールボックスを持つスタンドアロン EOP 組織が含まれます。
  
  - Standard [Preset Security Policy](configure-your-spam-filter-policies.md)および**Strict Preset Security Policy という名前のスパム対策ポリシー**。 **Standard Preset Security Policy**
  - [標準のプセットの](configure-anti-malware-policies.md)**セキュリティ ポリシーおよび Strict** **Preset Security Policy という名前のマルウェア対策ポリシー**。
  - [標準プレセット セキュリティ ポリシーおよび](set-up-anti-phishing-policies.md#spoof-settings) **Standard Preset Security Policy** **Strict Preset Security Policy (Spoof** settings) という名前の EOP フィッシング対策ポリシー。

- **Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または Office 365 の ATP アドオン サブスクリプションを持つ組織が含まれます。

  - 標準プレセットセキュリティ ポリシーと Strict **Preset Security Policy** という名前の ATP **フィッシング対策ポリシー。次**のポリシーが含まれます。

    - EOP フ [ィッシング](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用できるのと同じスプーフィング設定。
    - [偽装の設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高度なフィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [標準のプレセット](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)のセキュリティ ポリシーおよび**Strict Preset Security Policy (標準のプレセット セキュリティ ポリシー) という名前の安全なリンク ポリシー**。 **Standard Preset Security Policy**

  - [「標準のプセットの](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)**セキュリティ ポリシー」と「Strict** **Preset Security Policy」という名前の安全な添付ファイル ポリシー**。

EOP 保護は、ATP 保護とは異なるユーザーに適用できる点に注意してください。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルのポリシー設定は変更できません。 **Standard および** **Strict のポリシー**設定値は、EOP と ATP セキュリティの[推奨設定Office説明されています](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前に設定されたセキュリティ ポリシーおよびその他のポリシーの優先順位

複数のポリシーがユーザーに適用されている場合は、次の順序が最高の優先度から最低の優先度の順に適用されます。

1. **高い保護プレセット** のセキュリティ ポリシー
2. **標準保護** プレセット セキュリティ ポリシー
3. カスタム セキュリティ ポリシー
4. 既定のセキュリティ ポリシー

つまり、高い保護ポリシーの設定は **、標準** 保護ポリシーの設定より優先されます。 **これは** 、カスタム ポリシーからの設定を上書きします。これは、既定のポリシーからの設定を上書きします。

## <a name="assign-preset-security-policies-to-users"></a>事前設定したセキュリティ ポリシーをユーザーに割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [設定済みのセキュリティ ポリシー **] ページに直接移動するには**、. <https://protection.office.com/presetSecurityPolicies>

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 事前設定されたセキュリティ ポリシーを構成するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 事前に設定されたセキュリティ ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>セキュリティ/コンプライアンス センターを&、事前設定のセキュリティ ポリシーをユーザーに割り当てる

1. セキュリティ コンプライアンス センターから&、脅威管理**ポリシーの** \> **Policy** \> **プレセットのセキュリティ ポリシーに移動します**。

2. [Standard **protection]** (保護または **[ Strict Protection)] で、[Edit]** を **クリックします**。

3. 標準**保護の適用ウィザードまたは****高い取り消し保護ウィザード**が開始します。 EOP 保護 **が適用されるには、EOP** 保護が適用される内部の [受信者を](#policies-in-preset-security-policies) 特定します。

   1. [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用する条件: **Applied if**

      - **受信者が次の場合**
      - **受信者が次のメンバーの場合**
      - **受信者のドメインが**

      一度に使用できる条件は 1 つのみですが、条件には複数の値を指定できます。 同じ条件に複数の値がある場合、OR ロジック (例、 _\<recipient1\>_ など) が使用されます _\<recipient2\>_ 。

   2. 選択した条件が、シェード セクションに表示されます。 そのセクションで、以下のボックス **をクリック** します。 しばらく待つと、一覧が表示され、値を選択できます。 または、値を入力してリストにフィルターを適用し、値を選択できます。 必要な回数だけこの手順を繰り返します。 個別の値を削除するには、値の **[削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。 条件全体を削除するには、条件の [ **削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。

   3. 別の条件を追加するには、[ **条件を追加] をクリック** し、残りの条件から選択します。 さまざまな条件では AND ロジック (およびなど) が _\<recipient1\>_ 使います _\<member of group 1\>_ 。

      上記の手順を繰り返して条件に値を追加し、条件が満たないか、不足するまでこの手順を繰り返します。

   4. 例外を追加するには、[条件の **追加] をクリックします**。 表示されるドロップダウンで、[いつ次の場合を除く" の下に条件 **を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. 組織が Office 365 ATP を使用している場合は、Office 365 **ATP** 保護が適用される内部の [受信者を特定するための手順に従う](#policies-in-preset-security-policies) 必要があります。

   設定と動作は、EOP 保護が手順 **に適用されるのとまったく同** じです。

   完了したら、**[次へ]** をクリックします。

5. [確認 **] の** 手順で選択した内容を確認し、[確認] を **クリックします**。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>セキュリティ コンプライアンス センターを&、既定のセキュリティ ポリシーの割り当てを変更する

標準保護または高い保護のセキュリティ**Standard protection**ポリシーを割り当てて変更する**手順**は、事前に設定されたセキュリティ ポリシーをユーザーに最初に割り[当ててから行う手順と同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。

既存の条件**と例外を保持****したままで、** 標準の保護または制限付き保護セキュリティ ポリシーを無効にするには、トグルを **[Disabled]** にスライドします。 ポリシーを有効にするには、トグルを有効に切り替 **えて有効にします**。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

標準保護または制限の保護のセキュリティ**ポリシー****がユーザー**に正常に割り当てられたことを確認するには、既定値が標準の保護設定と**異なる保護**設定を使用します。これは **、[制限する保護] 設定とは異**なります。

たとえば、(信頼度の高いスパムでない) 電子メールの場合は、メッセージが標準保護ユーザーの [迷惑メール] フォルダー **に配信され** 、厳密に **保護ユーザーの場合は検疫** されます。

または、バ [ルク メールの場合](bulk-complaint-level-values.md)は、BCL 値 6 以上が標準保護ユーザー用迷惑メール フォルダー **にメッセージを配信し** 、BCL 値 4 以上で厳密な保護ユーザーに向け **、メッセージを検疫したことを確認** します。
