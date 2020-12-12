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
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 の保護機能に対して標準ポリシー設定と厳密ポリシー設定を適用する方法について説明します。
ms.openlocfilehash: a77201835652fb36822fbc603f5211c1f7a9521b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659252"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP と Microsoft Defender のセキュリティ ポリシーを Office 365 用に事前に設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシングポリシーを一度にユーザーに適用する一元的な場所を提供します。 ポリシー設定は構成できません。 代わりに、ユーザーは弊社が設定し、作業を中断することなく有害なコンテンツをユーザーから遠く離すバランスを取るデータセンターでの観察とエクスペリエンスに基づいておきます。

このトピックの残りの部分では、事前設定されたセキュリティ ポリシーと、その構成方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>事前設定されたセキュリティ ポリシーの種類

事前設定されたセキュリティ ポリシーは、次の要素で構成されます。

- プロファイル
- Policies
- ポリシー設定

また、複数の事前設定されたセキュリティ ポリシーと他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。

### <a name="profiles-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのプロファイル

プロファイルは、保護のレベルを決定します。 次のプロファイルを使用できます。

- **標準保護**: ほとんどのユーザーに適したベースライン保護プロファイルです。
- **厳密な保護**: 選択したユーザー (高い値のターゲットまたは優先度のユーザー) に対して、より積極的な保護プロファイル。

プロファイルが適用されるユーザーまたは適用されていないユーザーを決定する条件と例外でルールを使用します。

各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

使用可能な条件と例外は次のとおりです。

- **受信者は、** 組織内のメールボックス、メール ユーザー、またはメール連絡先です。
- **受信者は、組織内の** グループのメンバーです。
- **受信者のドメインは、Microsoft** 365 で構成されている承認されたドメインです。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーでは、EOP と Microsoft Defender for Office 365 のさまざまな保護機能の対応するポリシーが使用されます。 これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーをユーザーに割り当てる **と** 作成されます。 これらのポリシーは変更できない。

- **Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロンの EOP 組織が含まれます。

  - [Standard](configure-your-spam-filter-policies.md) Preset Security Policy and Strict **Preset Security Policy** という名前 **のスパム対策ポリシー**。
  - [Standard](configure-anti-malware-policies.md) Preset Security Policy and Strict **Preset Security Policy** という名前 **のマルウェア対策ポリシー**。
  - Standard Preset Security Policy および Strict Preset **Security** **Policy** (spoof settings) という名前の [EOP](set-up-anti-phishing-policies.md#spoof-settings)フィッシング対策ポリシー。

- **Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender for Office 365 アドオン サブスクリプションを持つ組織が含まれます。

  - Standard **Preset** Security Policy と Strict **Preset** Security Policy という名前の Office 365 用の Microsoft Defender のフィッシング対策ポリシー。次のものが含まれます。

    - EOP [フィッシング詐欺](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用可能なスプーフィング設定と同じ。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Standard Preset Security Policy and](set-up-atp-safe-links-policies.md) Strict Preset Security **Policy** という **名前の安全なリンク ポリシー**。

  - [Standard Preset Security Policy and](set-up-atp-safe-attachments-policies.md) Strict Preset Security **Policy** という **名前の安全な添付ファイル ポリシー**。

EOP 保護は、Microsoft Defender とは異なるユーザーに適用して、365 Office適用できます。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルのポリシー設定は変更できない。 Standard **および Strict** ポリシー **の設定値** については [、「365](recommended-settings-for-eop-and-office365-atp.md)セキュリティを強化する EOP および Microsoft Defender の推奨Office説明されています。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位

ユーザーに複数のポリシーが適用されると、次の順序が最高の優先度から最も低い優先度に適用されます。

1. **厳密な保護の** 事前設定のセキュリティ ポリシー
2. **標準の保護の** 事前設定セキュリティ ポリシー
3. カスタム セキュリティ ポリシー
4. 既定のセキュリティ ポリシー

つまり **、Strict** 保護ポリシーの設定は Standard 保護ポリシーの設定より優先され、カスタム ポリシーの設定は上書きされ、既定のポリシーの設定は上書きされます。

## <a name="assign-preset-security-policies-to-users"></a>ユーザーに事前設定されたセキュリティ ポリシーを割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [事前設定されたセキュリティ ポリシー **] ページに直接移動するには、次** の値を使用します <https://protection.office.com/presetSecurityPolicies> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - 事前設定されたセキュリティ ポリシーを構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - 事前に設定されたセキュリティ ポリシーへの読み取り専用アクセスでは、グローバル 閲覧者役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>セキュリティ/コンプライアンス センター&使用して、ユーザーに事前設定されたセキュリティ ポリシーを割り当てる

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシーの** 事前設定のセキュリティ ポリシー \>  \> **に移動します**。

2. [**標準の保護] または [****厳密な保護] で、[** 編集] を **クリックします**。

3. [**標準保護の適用] または [****厳密な保護の適用] ウィザード** が起動します。 **EOP 保護が手順に適用** される場合は [、EOP](#policies-in-preset-security-policies)保護が適用される内部受信者を特定します。

   1. [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用] の下の条件を **選択します**。

      - **受信者が次の場合**
      - **受信者は次のメンバーです。**
      - **受信者のドメインは次のとおりです。**

      条件は 1 回のみ使用できますが、条件に複数の値を指定できます。 同じ条件の複数の値は、OR ロジック (たとえば、or) を使用 _\<recipient1\>_ します _\<recipient2\>_ 。

   2. 選択した条件は、影付きのセクションに表示されます。 このセクションで、[Any of **these] ボックスをクリック** します。 しばらく待つ場合は、値を選択できるようリストが表示されます。 または、値の入力を開始してリストをフィルター処理し、値を選択できます。 必要な回数だけこの手順を繰り返します。 個々の値を削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。 条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   3. 別の条件を追加するには、[条件の追加 **] をクリック** し、残りの条件から選択します。 条件が異なる場合は、AND ロジック (例: _\<recipient1\>_ and) を使用します _\<member of group 1\>_ 。

      前の手順を繰り返して条件に値を追加し、必要な回数、または条件が足りないまでこの手順を繰り返します。

   4. 例外を追加するには、[条件の追加 **] をクリックします**。 表示されるドロップダウンで、[次の場合を除く] **で条件を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. 組織に Office 365 用 Microsoft Defender がある場合は **、ATP** 保護が適用される手順に進み [、Microsoft Defender for Office 365](#policies-in-preset-security-policies) の保護が適用される内部受信者を特定します。

   設定と動作は **、EOP 保護が手順に適用されるのとまったく同** じになります。

   完了したら、**[次へ]** をクリックします。

5. [確認 **] の** 手順で、選択内容を確認し、[確認] をクリック **します**。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>セキュリティ/コンプライアンス センター&使用して、事前設定されたセキュリティ ポリシーの割り当てを変更する

Standard Protection または **Strict** **Protection** セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーをユーザーに最初に割り当てた場合 [と同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。

既存の条件 **と例外を** 保持しながら、標準保護または **厳密** な保護のセキュリティ ポリシーを無効にするには、トグルを [無効] にスライド **します**。 ポリシーを有効にするには、トグルを [有効] に **スライドします**。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

標準の保護または厳密な保護のセキュリティ ポリシーがユーザーに正常に割り当てられたか確認するには、既定値が [標準] 保護設定とは異なる保護設定を使用します。これは[**厳密** な保護] 設定とは異なります。 

たとえば、スパムとして検出された (信頼度の高いスパムではない) メールの場合、メッセージが **Standard Protection** ユーザーの迷惑メール フォルダーに配信され **、Strict 保護** ユーザーに対して検疫済みである必要があります。

または、バルク [](bulk-complaint-level-values.md)メールの場合は、BCL 値 6 以上が **Standard Protection** ユーザーの迷惑メール フォルダーにメッセージを配信し、BCL 値 4 以上が **Strict** 保護ユーザーのメッセージを検疫します。
