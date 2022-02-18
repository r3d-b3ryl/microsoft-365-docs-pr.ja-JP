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
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、標準ポリシーと厳密なポリシー設定を、Exchange Online Protection (EOP) と Microsoft Defender の保護機能全体に適用する方法をOffice 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ff81eea4232693662a907695ea0cef0d94941ac6
ms.sourcegitcommit: 23a90ed17cddf3b0db8d4084c8424f0fabd7b1de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2022
ms.locfileid: "62887256"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP と Microsoft Defender でセキュリティ ポリシーを事前に設定Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用する一元的な場所を提供します。 ポリシー設定は構成できません。 代わりに、それらは弊社によって設定され、有害なコンテンツをユーザーから遠く離し、不必要な中断を回避するバランスを取るデータセンターでの観察と経験に基づいて行われます。

この記事の残りの部分では、事前設定されたセキュリティ ポリシーと、それらを構成する方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>事前設定されたセキュリティ ポリシーの構成

事前設定されたセキュリティ ポリシーは、次の要素で構成されます。

- プロファイル
- ポリシー
- ポリシー設定

さらに、複数の事前設定されたセキュリティ ポリシーや他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。

### <a name="profiles-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのプロファイル

プロファイルは、保護のレベルを決定します。 次のプロファイルを使用できます。

- **標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。
- **厳密な保護**: 選択したユーザー (高価値ターゲットまたは優先ユーザー) の保護プロファイルを積極的に設定します。

  標準 **保護と****厳密な保護では**、プロファイルが適用されるユーザーまたは適用されないユーザーを決定する条件と例外を含むルールを使用します。

  使用可能な条件と例外は次のとおりです。

  - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
  - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
  - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

- **組み込みの保護** (Defender for Office 365): リンクと添付ファイルセーフのセーフを有効にするプロファイル。 このプロファイルは、既定のポリシーを持セーフリンクセーフ添付ファイルの既定のポリシーを効果的に提供します。

  組 **み込み保護の** 場合、既定では、すべての Defender で既定でセキュリティ ポリシーがオンOffice 365されます。 お勧めしませんが、ユーザー、グループ、およびドメインに基づいて例外を構成して、保護が特定のユーザーに適用されなくすることもできます。

ユーザーにポリシーを割り当てるまで、 **Standard** および **Strict** の事前設定されたセキュリティ ポリシーは誰にも割り当てられていない。 これに対し、 **組み込みの保護** プリセット セキュリティ ポリシーは既定ですべての受信者に割り当てられますが、例外を構成できます。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーでは、EOP および Microsoft Defender の各種保護機能の対応するポリシーを使用Office 365。 これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーを **ユーザー** に割り当てると作成されます。 これらのポリシーの設定は変更できない。

- **Exchange Online Protection (EOP)** ポリシー: これには、Microsoft 365メールボックスを持Exchange Onlineスタンドアロンの EOP 組織が含まれます。Exchange Onlineします。

  - [Standard Preset Security Policy と](configure-your-spam-filter-policies.md) **Strict Preset Security Policy という** 名前の **スパム対策ポリシー**。
  - [Standard Preset Security Policy と](configure-anti-malware-policies.md) **Strict Preset Security Policy という** 名前の **マルウェア対策ポリシー**。
  - [標準プリセット セキュリティ ポリシーと](set-up-anti-phishing-policies.md#spoof-settings)厳密な事前設定セキュリティ ポリシー (スプーフィング設定) という EOP フィッシング **対策** ポリシー。

- **Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5サブスクリプション用の Microsoft 365 E5または Defender を持つ組織Office 365が含まれます。
  - Microsoft Defender のフィッシング対策ポリシーは、標準Office 365セキュリティ ポリシーと厳密な事前設定セキュリティ ポリシーと呼び、次のものが含まれます。
    - EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [セーフセキュリティ ポリシー、](set-up-safe-links-policies.md)**厳密な** 事前設定セキュリティ ポリシー、組み込み保護ポリシーという名前のリンク **ポリシー**。
  - [セーフセキュリティ ポリシー、](set-up-safe-attachments-policies.md)**厳密な** 事前設定セキュリティ ポリシー、組み込みの保護ポリシーという名前の添付ファイル **ポリシー**。

EOP 保護は、Microsoft Defender 以外のユーザーに適用して、Office 365できます。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルでポリシー設定を変更できない。 標準 **、****厳密、および組み** 込みの保護ポリシーの設定値については、「[EOP および Microsoft Defender](recommended-settings-for-eop-and-office365.md) のセキュリティに関する推奨設定Office 365されています。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位

複数のポリシーがユーザーに適用される場合、次の順序が優先度の高い順から優先度の低い順に適用されます。

1. **厳密な保護事前** 設定のセキュリティ ポリシー
2. **標準の保護の** 事前設定されたセキュリティ ポリシー
3. カスタム セキュリティ ポリシー
4. **組み込みの保護の事前** 設定されたセキュリティ ポリシーと既定のセキュリティ ポリシー

つまり、厳密な保護ポリシーの設定は、カスタム ポリシーの設定を上書きする標準保護ポリシーの設定を上書きします。これは、組み込みの保護事前設定セキュリティ ポリシー (セーフ Links および セーフ Attachments) と既定のポリシー (スパム対策、マルウェア対策、フィッシング対策) の設定を上書きします。

たとえば、標準保護にセキュリティ設定が存在し、管理者がユーザーの標準保護を有効にしている場合、標準保護設定は、カスタム ポリシーまたは既定のポリシー (同じユーザーの場合) の設定に対して構成されている設定の代わりに適用されます。 特定のニーズを満たすために組織内の他のユーザーにカスタム ポリシーを適用する際に、標準または厳密な保護ポリシーのみを適用する組織の一部が所属している場合があります。

**組み込みの保護は**、既存のリンクまたは添付ファイルポリシーセーフ受信者セーフ影響を与えかねない。 標準保護、厳密な保護、またはカスタム セーフ リンクまたは セーフ 添付ファイル ポリシーを既に構成している場合、これらのポリシーは常に組み込み保護の前に適用されます。既存の事前設定ポリシーまたはカスタム ポリシーで既に定義されている受信者には影響はありません。 

## <a name="assign-preset-security-policies-to-users"></a>ユーザーに事前設定されたセキュリティ ポリシーを割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/presetSecurityPolicies>。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 事前設定されたセキュリティ ポリシーを構成するには、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。
  - 事前設定されたセキュリティ ポリシーへの読み取り専用アクセスでは、グローバル リーダー役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: ユーザーを Azure Active Directory の対応する Microsoft 365 管理センター ロールに追加すると、ユーザーはユーザーに対して、Microsoft 365 の他の機能に対して必要なアクセス許可とアクセス許可を与Microsoft 365。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>標準および厳密Microsoft 365 Defenderセキュリティ ポリシーをユーザーに割り当てるには、Microsoft 365 Defender ポータルを使用します。

1. [ポリシー] Microsoft 365 Defender  \>  \>  \> <https://security.microsoft.com>で、[テンプレート ポリシー] セクションの&ルール脅威ポリシー&セキュリティ ポリシーの事前設定をメールで送信する」 に **移動** します。 [事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/presetSecurityPolicies>。

2. [事前設定 **されたセキュリティ ポリシー] ページで**、[標準 **保護] セクション** または [厳密な保護] セクションの [管理 **] を** クリックします。

3. [ **標準保護の適用] または** **[厳密な保護の適用]** ウィザードは、フライアウトで開始します。 **[EOP 保護] ページで**、[EOP](#policies-in-preset-security-policies) 保護が適用される内部受信者 (受信者の条件) を特定します。
   - **ユーザー**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. microsoft Defender for Office 365 組織では、**Office 365** 保護が適用されるページに対して Defender に連れて行き、[microsoft Defender for Office 365](#policies-in-preset-security-policies) 保護が適用される内部受信者 (受信者の条件) を特定します。

   設定と動作は、前の手順の **ページに適用される EOP** 保護とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. [変更 **の確認と確認] ページで** 、選択内容を確認し、[確認] をクリック **します**。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>標準および厳密Microsoft 365 Defenderセキュリティ ポリシーの割り当てを変更するには、このポータルを使用します。

Standard Protection または Strict **Protection** プリセット セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーを最初にユーザーに割り当てた場合と [同じです](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users)。

既存の条件と例外 **を** 維持しながら、標準保護または厳密な保護の事前設定のセキュリティ ポリシーを無効にするには、トグルを [無効] トグル オフ **に**![スライドします。](../../media/scc-toggle-off.png) ポリシーを有効にするには、トグルを [有効] トグル **オンにスライド**![します](../../media/scc-toggle-on.png)。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>組み込Microsoft 365 Defenderセキュリティ ポリシーの割り当てを変更するには、このポータルを使用します。

組み込みの保護事前設定のセキュリティ ポリシーは、すべての受信者に割り当てられているので、標準保護ポリシーまたは厳密な保護事前設定セキュリティ  ポリシー、またはカスタム セーフ リンクまたは セーフ 添付ファイル ポリシーで定義されている受信者には影響を及ぼします。

そのため、通常、組み込みの保護の事前設定されたセキュリティ ポリシーに **対する例外は** 推奨しません。

1. [ポリシー] Microsoft 365 Defender  \>  \>  \> <https://security.microsoft.com>で、[テンプレート ポリシー] セクションの&ルール脅威ポリシー&セキュリティ ポリシーの事前設定をメールで送信する」 に **移動** します。 [事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/presetSecurityPolicies>。

2. [セキュリティ **ポリシーの事前設定] ページ** で、[組み込みの保護] セクションで [除外の追加 (推奨しない **)****] を選択** します。

3. 表示される **[組** み込み保護から除外する] フライアウトで、組み込みの セーフ リンクと添付ファイル保護から除外される内部受信者セーフします。
   - **ユーザー**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   完了したら、**[保存]** をクリックします。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

標準保護または厳密な保護セキュリティ ポリシーがユーザーに正常に割り当てられているか確認するには、既定値が標準保護設定とは異なる保護設定を使用します。これは、厳密な保護設定とは異なります。

たとえば、スパムとして検出された (信頼度の高いスパムではない) 電子メールの場合、メッセージが標準保護ユーザーの迷惑メール フォルダーに配信され、厳密な保護ユーザーに対して検疫済みである必要があります。

または、バルク [](bulk-complaint-level-values.md)メールの場合は、BCL 値 6 以上が標準保護ユーザーの迷惑メール フォルダーにメッセージを配信し、BCL 値 4 以上が厳密な保護ユーザーのメッセージを検疫します。
