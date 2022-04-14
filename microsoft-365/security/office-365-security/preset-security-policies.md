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
description: 管理者は、Exchange Online Protection (EOP) とMicrosoft Defender for Office 365の保護機能全体に Standard および Strict ポリシー設定を適用する方法を学習できます
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a74fce0242f0206218d6f7f2f13e61d9f0a3b6f
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847117"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

事前設定されたセキュリティ ポリシーにより、推奨されるすべてのスパム、マルウェア、フィッシング ポリシーをユーザーに一度に適用するための一元的な場所が提供されます。 ポリシー設定は構成できません。 代わりに、これらは Microsoft によって設定され、有害なコンテンツをユーザーから遠ざけることと、不要な中断を回避することのバランスを取るための、データセンターでの観察と経験に基づいています。

この記事の残りの部分では、事前設定されたセキュリティ ポリシーとその構成方法について説明します。

## <a name="what-preset-security-policies-are-made-of"></a>事前設定されたセキュリティ ポリシーの構成内容

事前設定されたセキュリティ ポリシーは、次の要素で構成されます。

- プロファイル
- ポリシー
- ポリシー設定

また、複数の事前設定されたセキュリティ ポリシーとその他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。

### <a name="profiles-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのプロファイル

プロファイルは、保護のレベルを決定します。 次のプロファイルを使用できます。

- **標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。
- **厳密な保護**: 選択したユーザー (高価値ターゲットまたは優先度の高いユーザー) に対して、より積極的な保護プロファイル。

  **Standard Protection** および **Strict Protection** では、条件と例外を含むルールを使用して、ポリシーが適用される内部受信者 (受信者の条件) を決定します。

  使用可能な条件と例外は次のとおりです。

  - **ユーザー**: 指定したメールボックス、メール ユーザー、またはメール連絡先。
  - **グループ**:
    - 指定した配布グループまたはメールが有効なセキュリティ グループのメンバー。
    - 指定したMicrosoft 365 グループ。
  - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

- **組み込みの保護** (Defender for Office 365のみ): セーフ リンクとセーフ添付ファイルの保護のみを有効にするプロファイル。 このプロファイルは、セーフ リンクとセーフ添付ファイルの既定のポリシーを効果的に提供します。このポリシーには既定のポリシーがありませんでした。

  **組み込み保護の** 場合、既定では、すべてのDefender for Office 365ユーザーに対して事前設定されたセキュリティ ポリシーがオンになっています。 お勧めしませんが、特定のユーザーに保護が適用されないように、 **ユーザー**、 **グループ**、 **ドメイン** に基づいて例外を構成することもできます。

ユーザーにポリシーを割り当てるまで、 **Standard** および **Strict** の事前設定済みセキュリティ ポリシーは誰にも割り当てなくなります。 これに対し、 **組み込みの保護** プリセット セキュリティ ポリシーは既定ですべての受信者に割り当てられますが、例外は構成できます。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーでは、EOP とMicrosoft Defender for Office 365のさまざまな保護機能の対応するポリシーが使用されます。 これらのポリシーは、**Standard Protection** または **Strict** Protection の事前設定されたセキュリティ ポリシーをユーザーに割り当てた _後_ に作成されます。 これらのポリシーの設定は変更できません。

- **Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを持つMicrosoft 365組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。

  - 標準プリセット セキュリティ ポリシーと Strict **Preset Security Policy** という名前 **の**[スパム対策](configure-your-spam-filter-policies.md)ポリシー。
  - Standard Preset Security Policy と Strict **Preset Security Policy** という名前の [マルウェア対策](configure-anti-malware-policies.md)**ポリシー**。
  - **Standard Preset Security Policy と Strict Preset Security Policy** (スプーフィング設定) という名前の [EOP フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings)**ポリシー**。

- **Microsoft Defender for Office 365 ポリシー**: これには、Microsoft 365 E5またはDefender for Office 365アドオン サブスクリプションを持つ組織が含まれます。
  - **Standard Preset Security Policy と Strict Preset Security Policy** という名前のMicrosoft Defender for Office 365のフィッシング対策 **ポリシー**。次のものが含まれます。
    - EOP フィッシング対策ポリシーで使用できるのと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [セーフ 標準](set-up-safe-links-policies.md)**プリセット セキュリティ ポリシー、Strict Preset Security Policy**、**および組み込み保護****ポリシー** という名前のリンク ポリシー。
  - セーフ **標準プリセット セキュリティ ポリシー、Strict Preset Security Policy**、および **組み込み保護** ポリシーという名前の [添付ファイル](set-up-safe-attachments-policies.md) **ポリシー**。

EOP 保護は、Microsoft Defender for Office 365保護とは異なるユーザーに適用できます。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルでポリシー設定を変更することはできません。 **Standard**、**Strict**、および **組み込みの保護** ポリシー設定の値については、「[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定」を参照](recommended-settings-for-eop-and-office365.md)してください。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティ ポリシーとその他のポリシーの優先順位

ユーザーに複数のポリシーが適用されている場合、優先度が最も高いものから最も低い優先度まで、次の順序が適用されます。

1. **厳格な保護** の事前設定されたセキュリティ ポリシー
2. **Standard Protection** 事前設定セキュリティ ポリシー
3. カスタム セキュリティ ポリシー
4. **組み込みの保護** プリセットのセキュリティ ポリシーと既定のセキュリティ ポリシー

言い換えると、**Strict Protection** ポリシーの設定は **Standard 保護** ポリシーの設定をオーバーライドします。これは、カスタム ポリシーの設定をオーバーライドします。組 **み込みの保護** プリセット セキュリティ ポリシー (セーフ リンクと添付ファイルセーフ) と既定のポリシー (スパム対策、マルウェア対策、フィッシング対策) の設定がオーバーライドされます。

たとえば、 **Standard Protection** にセキュリティ設定が存在し、管理者がユーザーの **Standard 保護** を有効にしている場合、カスタム ポリシーまたは既定のポリシー (同じユーザー) でその設定に対して構成されている設定ではなく、 **Standard 保護** 設定が適用されます。 特定のニーズを満たすために、組織内の他のユーザーにカスタム ポリシーを適用するときに **、標準** または **厳格な保護** ポリシーのみを適用する組織の一部が存在する場合があることに注意してください。

**組み込みの保護** は、既存のセーフ リンクポリシーまたはセーフ添付ファイル ポリシーの受信者には影響しません。 **Standard Protection**、**Strict Protection**、またはカスタム セーフ リンクまたはセーフ添付ファイル ポリシーを既に構成している場合、これらのポリシーは **組み込み保護**_の前に__常に_ 適用されるため、既存のプリセットポリシーまたはカスタム ポリシーで既に定義されている受信者には影響しません。

## <a name="assign-preset-security-policies-to-users"></a>事前設定されたセキュリティ ポリシーをユーザーに割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 事前設定されたセキュリティ ポリシーを構成するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 事前設定されたセキュリティ ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: Microsoft 365 管理センターの対応するAzure Active Directory ロールにユーザーを追加すると、Microsoft 365の他の機能に必要なアクセス許可 _と_ アクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Microsoft 365 Defender ポータルを使用して、Standard および Strict の事前設定済みセキュリティ ポリシーをユーザーに割り当てる

1. Microsoft 365 Defender ポータルの [**テンプレート** ポリシー] セクション **の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **プリセット セキュリティ ポリシー**] に移動します。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

2. **[事前設定されたセキュリティ ポリシー**] ページの [**Standard Protection**] セクションまたは [**Strict protection**] セクションで [**管理**] をクリックします。

3. **標準保護の適用** または **厳格な保護の適用** ウィザードはポップアップで開始されます。 **EOP 保護が適用される** ページで、[EOP 保護](#policies-in-preset-security-policies)が適用される内部受信者 (受信者の条件) を特定します。
   - **Users**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

4. Microsoft Defender for Office 365組織では、Microsoft Defender for Office 365保護が適用される内部受信者を識別 **するためにページに適用** される [Defender for Office 365保護](#policies-in-preset-security-policies)に移動します (受信者の条件)。

   設定と動作は、前の手順のページ **に適用される EOP 保護** とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. [ **変更の確認と確認** ] ページで、選択内容を確認し、[ **確認**] をクリックします。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Microsoft 365 Defender ポータルを使用して、Standard および Strict の事前設定済みセキュリティ ポリシーの割り当てを変更する

**Standard Protection** または **Strict Protection** プリセット セキュリティ ポリシーの割り当てを変更する手順は、事前設定 [されたセキュリティ ポリシーをユーザーに最初に割り当てた](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users)場合と同じです。

既存の条件と例外を保持したまま **Standard Protection** または **Strict Protection** の事前設定されたセキュリティ ポリシーを無効にするには、トグルを **[無効]** ![トグル オフにスライドします](../../media/scc-toggle-off.png)。 ポリシーを有効にするには、トグルを [**有効**![] トグルオン](../../media/scc-toggle-on.png)にスライドします。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Microsoft 365 Defender ポータルを使用して、組み込みの保護プリセット セキュリティ ポリシーの割り当てを変更する

**組み込みの保護** プリセット セキュリティ ポリシーはすべての受信者に割り当てられ、**Standard Protection** または **Strict Protection** プリセット セキュリティ ポリシー、またはカスタム セーフ リンクポリシーまたはセーフ添付ファイル ポリシーで定義されている受信者には影響しません。

そのため、通常は **、組み込みの保護** プリセット セキュリティ ポリシーに例外を推奨しません。

1. Microsoft 365 Defender ポータルの [**テンプレート** ポリシー] セクション **の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **プリセット セキュリティ ポリシー**] に移動します。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

2. **[事前設定されたセキュリティ ポリシー**] ページの [**組み込みの保護**] セクションで [**除外の追加 (推奨されません)]** を選択します。

3. 表示される [**組み込みの保護から除外**] ポップアップで、組み込みのセーフ リンクとセーフ添付ファイル保護から除外される内部受信者を特定します。
   - **Users**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   完了したら、**[保存]** をクリックします。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

**Standard Protection** または **Strict Protection** セキュリティ ポリシーがユーザーに正常に割り当てられていることを確認するには、標準保護設定とは異なる標準 **保護** 設定と既定値が異なる **保護** 設定を使用します。

たとえば、スパムとして検出された電子メール (信頼度の高いスパムではない) の場合、 **メッセージが Standard 保護** ユーザーの迷惑メール フォルダーに配信され、 **Strict Protection** ユーザー用に検疫されていることを確認します。

または、 [一括メール](bulk-complaint-level-values.md)の場合は、BCL 値 6 以上が **標準保護** ユーザーの迷惑メール フォルダーにメッセージを配信し、BCL 値 4 以上が **Strict Protection** ユーザーのメッセージを検疫することを確認します。
