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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender for Office 365 の保護機能全体に標準ポリシー設定と厳密なポリシー設定を適用する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57c13517d9fd41bcafea5c9d672da0e6b581ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926762"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP および Microsoft Defender の 365 用に事前設定Officeポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用する一元的な場所を提供します。 ポリシー設定は構成できません。 代わりに、それらは当社によって設定され、有害なコンテンツをユーザーから離れ、作業を中断することなく維持するバランスを取るデータセンターでの観察と経験に基づいて行われます。

このトピックの残りの部分では、事前設定されたセキュリティ ポリシーと、それらを構成する方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>事前設定されたセキュリティ ポリシーの構成

事前設定されたセキュリティ ポリシーは、次の要素で構成されます。

- プロファイル
- Policies
- ポリシー設定

さらに、複数の事前設定されたセキュリティ ポリシーや他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。

### <a name="profiles-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのプロファイル

プロファイルは、保護のレベルを決定します。 次のプロファイルを使用できます。

- **標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。
- **厳密な保護**: 選択したユーザー (高価値のターゲットまたは優先度の高いユーザー) に対して、より積極的な保護プロファイルを作成します。

プロファイルが適用されるユーザーまたは適用されないユーザーを決定する条件と例外を含むルールを使用します。

各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

使用可能な条件と例外は次のとおりです。

- **受信者は、組織内** のメールボックス、メール ユーザー、またはメール連絡先です。
- **受信者は、組織内の**: グループのメンバーです。
- **受信者ドメインは、Microsoft** 365 で構成されている受け入れドメインです。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーでは、EOP および Microsoft Defender の各種保護機能の対応するポリシーを、Office使用します。 これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーを **ユーザー** に割り当てると作成されます。 これらのポリシーは変更できない。

- **Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。

  - [Standard](configure-your-spam-filter-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **スパム対策ポリシー**。
  - [Standard](configure-anti-malware-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **マルウェア対策ポリシー**。
  - [標準プリセット セキュリティ ポリシーと](set-up-anti-phishing-policies.md#spoof-settings)厳密な事前設定セキュリティ ポリシー (スプーフィング設定) という EOP フィッシング **対策** ポリシー。

- **Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender が 365 アドオン サブスクリプションの組織Office含まれます。

  - Microsoft Defender のフィッシング対策ポリシーは、標準Officeセキュリティ ポリシーと厳密な事前設定セキュリティ ポリシーという名前の 365 を使用します。このポリシーには、次のものが含まれます。

    - EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Standard Preset Security Policy と](set-up-atp-safe-links-policies.md) Strict Preset Security Policy **という** 名前のセーフ リンク **ポリシー**。

  - [Standard Preset Security](set-up-atp-safe-attachments-policies.md) Policy と **Strict Preset Security Policy という** 名前の **安全な添付ファイル ポリシー**。

365 保護の場合は、Microsoft Defender とは異なるユーザーに EOP Office適用できます。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルでポリシー設定を変更できない。 標準 **ポリシーと****厳密なポリシー** 設定の値については、「EOP および Microsoft Defender の [365](recommended-settings-for-eop-and-office365-atp.md)セキュリティに関する推奨Office説明されています。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位

複数のポリシーがユーザーに適用される場合、次の順序が優先度の高い順から優先度の低い順に適用されます。

1. **厳密な保護事前** 設定のセキュリティ ポリシー
2. **標準の保護の** 事前設定されたセキュリティ ポリシー
3. カスタム セキュリティ ポリシー
4. 既定のセキュリティ ポリシー

つまり、厳密な保護ポリシーの設定は、既定のポリシーの設定を上書きするカスタム ポリシーの設定を上書きする標準保護ポリシーの設定を上書きします。

## <a name="assign-preset-security-policies-to-users"></a>ユーザーに事前設定されたセキュリティ ポリシーを割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://protection.office.com/presetSecurityPolicies> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 事前設定されたセキュリティ ポリシーを構成するには、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。
  - 事前設定されたセキュリティ ポリシーへの読み取り専用アクセスでは、グローバル リーダー役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 の他の機能に必要なアクセス許可とアクセス許可がユーザーに付与されます。 詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>コンプライアンス センターのセキュリティ &を使用して、ユーザーに事前設定されたセキュリティ ポリシーを割り当てる

1. セキュリティ ポリシー コンプライアンス &で、[**脅威管理ポリシー** の事前設定] \>  \> **のセキュリティ ポリシーに移動します**。

2. [標準 **保護] または [****厳密な保護] で、[** 編集] を **クリックします**。

3. [ **標準保護の適用] または** **[厳密な保護の適用] ウィザードが** 起動します。 手順に **適用される EOP** 保護で [、EOP](#policies-in-preset-security-policies) 保護が適用される内部受信者を特定します。

   1. [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。

      - **受信者は次のとおりです。**
      - **受信者は、次のメンバーです。**
      - **受信者ドメインは、次のとおりです。**

      条件を使用できるのは 1 回のみですが、条件に複数の値を指定できます。 同じ条件の複数の値は、OR ロジック (たとえば、または) を _\<recipient1\>_ 使用します _\<recipient2\>_ 。

   2. 選択した条件が影付きセクションに表示されます。 そのセクションで、[これらの任意] **ボックスをクリック** します。 しばらく待つ場合は、値を選択できるようリストが表示されます。 または、値の入力を開始してリストをフィルター処理し、値を選択できます。 必要な回数だけこの手順を繰り返します。 個々の値を削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。 条件全体を削除するには、条件の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   3. 別の条件を追加するには、[条件の **追加] をクリックし** 、残りの条件から選択します。 条件が異なる場合は、AND ロジック (たとえば、および _\<recipient1\>_ ) を使用 _\<member of group 1\>_ します。

      前の手順を繰り返して条件に値を追加し、必要な回数、または条件が満たされるまでこの手順を繰り返します。

   4. 例外を追加するには、[条件の追加 **] をクリックします**。 表示されるドロップダウンで、[条件] で [条件を指定する場合を **除く] を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. 組織に microsoft Defender for Office 365 がある場合は **、ATP** 保護が適用される手順に進み、microsoft Defender for [Office 365](#policies-in-preset-security-policies) 保護が適用される内部受信者を特定します。

   設定と動作は **、EOP 保護が手順に適用されるのとまったく同** じです。

   完了したら、**[次へ]** をクリックします。

5. [確認 **] 手順** で、選択内容を確認し、[確認] を **クリックします**。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>コンプライアンス センターのセキュリティ &使用して、事前設定されたセキュリティ ポリシーの割り当てを変更する

Standard Protection または **Strict** **Protection** セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーをユーザーに最初に割り当てた場合と [同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。

既存の条件と例外 **を** 維持しながら、標準保護ポリシーまたは **厳密** な保護セキュリティ ポリシーを無効にするには、トグルを [無効] に **スライドします**。 ポリシーを有効にするには、トグルを [有効] に **スライドします**。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

標準保護または厳密な保護セキュリティ ポリシーがユーザーに正常に割り当てられているか確認するには、既定値が標準保護設定とは異なる保護設定を使用します。これは、厳密な保護設定とは異なります。

たとえば、スパムとして検出された (信頼度の高いスパムではない) 電子メールの場合、メッセージが標準保護ユーザーの迷惑メールフォルダーに配信され、厳密な保護ユーザーに対して検疫済みである必要があります。

または、バルク メールの場合は、BCL 値 6 以上が標準保護ユーザーの迷惑メールフォルダーにメッセージを配信し、BCL 値 4 以上が厳密な保護ユーザーのメッセージを検疫します。 [](bulk-complaint-level-values.md)