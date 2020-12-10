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
description: 管理者は、Exchange Online Protection (EOP) および Microsoft Defender for Office 365 の保護機能において標準ポリシー設定と厳密なポリシー設定を適用する方法を学習できます。
ms.openlocfilehash: fb613916ec375214b33b8b842c6817561920715d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616046"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP および Microsoft Defender for Office 365 の事前設定されたセキュリティポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


事前設定されたセキュリティポリシーにより、すべての推奨されるスパム、マルウェア、およびフィッシングポリシーをユーザーに一度に適用するための一元的な場所が提供されます。 ポリシー設定は構成できません。 その代わりに、ユーザーは microsoft によって設定され、問題のあるコンテンツをユーザーに保持していなくても、作業を中断することなくバランスを取るために、データセンターの観察とエクスペリエンスに基づいています。

このトピックの残りの部分では、事前設定されたセキュリティポリシーとそれらを構成する方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>事前設定されたセキュリティポリシーの内容

事前設定されたセキュリティポリシーは、次の要素で構成されます。

- プロファイル
- Policies
- ポリシー設定

また、複数の事前設定されたセキュリティポリシーやその他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。

### <a name="profiles-in-preset-security-policies"></a>事前設定されるセキュリティポリシーのプロファイル

プロファイルは、保護レベルを決定します。 次のプロファイルを使用できます。

- **標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。
- **厳重な保護**: 選択したユーザーのために、より厳しい保護プロファイルを使用します (高価値のターゲットまたは優先度の高いユーザー)。

ルールは、プロファイルが適用されているかどうかを決定する条件と例外を指定して使用します。

各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

使用可能な条件と例外は次のとおりです。

- **受信者は**、組織内のメールボックス、メールユーザー、またはメール連絡先です。
- **受信者が** 組織内のグループのメンバーである。
- **受信者のドメインは、** Microsoft 365 で構成されている承認済みドメインです。

### <a name="policies-in-preset-security-policies"></a>事前設定されるセキュリティポリシーのポリシー

事前設定されたセキュリティポリシーでは、EOP のさまざまな保護機能と Microsoft Defender for Office 365 の対応するポリシーが使用されます。 これらのポリシーは、**標準保護** または厳格な **保護** の事前設定のセキュリティポリシーをユーザーに割り当てた _後_ に作成されます。 これらのポリシーを変更することはできません。

- **Exchange Online Protection (EOP) ポリシー**: これには、exchange online メールボックスを使用する Microsoft 365 組織と、exchange online メールボックスを持たないスタンドアロン EOP 組織が含まれます。

  - **標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前 [のスパム対策ポリシー](configure-your-spam-filter-policies.md) 。
  - **標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前 [のマルウェア対策ポリシー](configure-anti-malware-policies.md) 。
  - EOP の **既定のセキュリティポリシー** および厳密な事前設定された **セキュリティポリシー** (スプーフィング設定) という名前の [フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)を設定します。

- **Microsoft Defender For office 365 ポリシー**: これには、office 365 アドオンサブスクリプションの Microsoft 365 E5 または Defender を使用する組織が含まれます。

  - Microsoft Defender のマルウェア対策ポリシー Office 365 の場合は、 **標準の事前設定** されたセキュリティポリシーと、次のような **厳格な事前設定セキュリティポリシー** が指定されています。

    - EOP のフィッシング対策ポリシーで使用可能なものと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [安全なリンク]**標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前の [ポリシー](set-up-atp-safe-links-policies.md) 。

  - [[安全な添付ファイル](set-up-atp-safe-attachments-policies.md)]**標準の既定のセキュリティポリシー** と、厳密に設定された **セキュリティポリシー** という名前のポリシー。

Microsoft Defender for Office 365 の保護とは異なるユーザーに EOP 保護を適用することができることに注意してください。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されるセキュリティポリシーのポリシー設定

保護プロファイルでポリシー設定を変更することはできません。 [ **標準** および **厳密** なポリシー設定] の値については、「 [EOP の推奨設定」および「office 365 のセキュリティのための Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)」を参照してください。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティポリシーおよびその他のポリシーの優先順位

ユーザーに複数のポリシーが適用されている場合、次の順序は、優先度の高いものから順に適用されます。

1. **厳格な保護** の事前設定セキュリティポリシー
2. **標準保護** の事前設定セキュリティポリシー
3. カスタムセキュリティポリシー
4. 既定のセキュリティポリシー

つまり、 **厳格な保護** ポリシーの設定は、 **標準保護** ポリシーの設定を上書きします。これは、カスタムポリシーの設定を上書きします。これにより、既定のポリシーの設定が上書きされます。

## <a name="assign-preset-security-policies-to-users"></a>事前設定されるセキュリティポリシーのユーザーへの割り当て

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [事前設定された **セキュリティポリシー** ] ページに直接移動するには、を使用 <https://protection.office.com/presetSecurityPolicies> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。

  - 事前設定されたセキュリティポリシーを構成するには、[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)で、**組織の管理** または **セキュリティ管理者** の役割のメンバーである必要があります。

  - 事前設定されたセキュリティポリシーに対する読み取り専用アクセスでは、[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の **グローバル閲覧** 者役割グループのメンバーである必要があります。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>セキュリティ & コンプライアンスセンターを使用して、事前に設定されたセキュリティポリシーをユーザーに割り当てる

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** ] \> **プリセットセキュリティポリシー** に移動します。

2. [ **標準保護** ] または [ **厳重な保護**] で、[ **編集**] をクリックします。

3. [ **標準保護を適用** する] または [ **厳格な保護を適用** する] ウィザードが起動します。 [ **EOP 保護の適用先** ] ステップで、 [EOP 保護](#policies-in-preset-security-policies) を適用する内部の受信者を特定します。

   1. [ **条件の追加] を** クリックします。 表示されるドロップダウンで、[適用済みの **場合**] の条件を選択します。

      - **受信者の**
      - **受信者がメンバーである**
      - **受信者のドメイン**

      条件は1回だけ使用できますが、条件に複数の値を指定することができます。 同じ条件の複数の値を使用するか、ロジックを指定します (例: _\<recipient1\>_ または _\<recipient2\>_ )。

   2. 選択した条件が影付きのセクションに表示されます。 そのセクションで、 **次のいずれか** のボックスをクリックします。 少し待つと、値を選択できるようにリストが表示されます。 または、値の入力を開始して、リストにフィルターを適用し、値を選択することもできます。 必要な回数だけこの手順を繰り返します。 個々の値を削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。 条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。

   3. 別の条件を追加するには、[ **条件の追加** ] をクリックし、残りの条件から選択します。 さまざまな条件とロジック (たとえば、と) が使用さ _\<recipient1\>_ _\<member of group 1\>_ れます。

      前の手順を繰り返して条件に値を追加し、必要に応じて、または条件が満たされなくなるまで、この手順を繰り返します。

   4. 例外を追加するには、[ **条件の追加**] をクリックします。 表示されたドロップダウンで、[ **when when**] の条件を選択します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. 組織が Microsoft Defender for Office 365 を使用している場合は、「 **ATP の保護を適用** 」の手順に進み、 [Microsoft defender for office 365 の保護](#policies-in-preset-security-policies) が適用される内部の受信者を特定します。

   設定と動作は、手順 **に適用される EOP 保護** とよく似ています。

   完了したら、**[次へ]** をクリックします。

5. [ **確認** ] 手順で選択内容を確認し、[ **確認**] をクリックします。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>セキュリティ & コンプライアンスセンターを使用して、事前設定されたセキュリティポリシーの割り当てを変更する

**標準保護** または **厳密保護** のセキュリティポリシーの割り当てを変更する手順は、最初 [に事前に設定したセキュリティポリシーをユーザーに割り当て](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)た場合と同じです。

既存の条件と例外を保持したまま、 **標準保護** または **厳格な保護** のセキュリティポリシーを無効にするには、[ **無効**] に切り替えます。 ポリシーを有効にするには、[オン] を **スライドします。**

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

**標準保護** または **厳格な保護** セキュリティポリシーがユーザーに正常に割り当てられたことを確認するには、保護設定を使用します。既定値は **標準保護** 設定とは異なります。これは **厳密な保護** 設定とは異なります。

たとえば、スパムとして検出された電子メール (高精度スパムではない) の場合は、メッセージが [迷惑メール]**フォルダーに配信** されていることを確認してください。

または、 [バルクメール](bulk-complaint-level-values.md)の場合は、bcl 値6以上が **標準の保護** ユーザー用の迷惑メールフォルダーにメッセージを配信していることを確認し、bcl 値4以上の検疫を使用して、 **厳正な保護** ユーザーにメッセージを送信します。
