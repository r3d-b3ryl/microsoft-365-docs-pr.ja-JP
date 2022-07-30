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
ms.openlocfilehash: bd5fd696a9e22f0e30d18b3b785761847166a5b3
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085249"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

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

  - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
  - **グループ**: 
    - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
    - 指定した Microsoft 365 グループ。
  - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

  > [!IMPORTANT]
  > 複数の異なる種類の条件や例外は加算されません。包括的です。 事前設定されたセキュリティ ポリシーは、指定 _されたすべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
  >
  > - 受信者は次のとおりです: romain@contoso.com
  > - 受信者が次のメンバーの場合: Executive
  >
  > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
  >
  > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

- **組み込みの保護** (Defender for Office 365のみ): 安全なリンクと安全な添付ファイルの保護のみを有効にするプロファイル。 このプロファイルは、安全なリンクと安全な添付ファイルの既定のポリシーを効果的に提供します。既定のポリシーは一度もありませんでした。

  > [!NOTE]
  > 組み込みの保護プリセット セキュリティ ポリシーが展開されており、組織では使用できない可能性があります。

  **組み込み保護の** 場合、既定では、すべてのDefender for Office 365ユーザーに対して事前設定されたセキュリティ ポリシーがオンになっています。 お勧めしませんが、特定のユーザーに保護が適用されないように、 **ユーザー**、 **グループ**、 **ドメイン** に基づいて例外を構成することもできます。

ユーザーにポリシーを割り当てるまで、 **Standard** および **Strict** の事前設定済みセキュリティ ポリシーは誰にも割り当てなくなります。 これに対し、 **組み込みの保護** プリセット セキュリティ ポリシーは既定ですべての受信者に割り当てられますが、例外は構成できます。

### <a name="policies-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー

事前設定されたセキュリティ ポリシーでは、EOP とMicrosoft Defender for Office 365のさまざまな保護機能の対応するポリシーが使用されます。 これらのポリシーは、**Standard Protection** または **Strict** Protection の事前設定されたセキュリティ ポリシーをユーザーに割り当てた _後_ に作成されます。 これらのポリシーの設定は変更できません。

- **Exchange Online Protection (EOP) ポリシー**: これらのポリシーは、Exchange Online メールボックスを持つすべての Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織にあります。

  - 標準プリセット セキュリティ ポリシーと Strict **Preset Security Policy** という名前 **の**[スパム対策](configure-your-spam-filter-policies.md)ポリシー。
  - Standard Preset Security Policy と Strict **Preset Security Policy** という名前の [マルウェア対策](configure-anti-malware-policies.md)**ポリシー**。
  - **Standard Preset Security** Policy と **Strict** Preset Security [Policy (スプーフィング設定) という名前のフィッシング対策ポリシー (スプーフィング保護)。](set-up-anti-phishing-policies.md#spoof-settings)

  > [!NOTE]
  > 送信スパム ポリシーは、事前設定されたセキュリティ ポリシーの一部ではありません。 既定の送信スパム ポリシーは、事前設定されたセキュリティ ポリシーのメンバーを自動的に保護します。 または、カスタム送信スパム ポリシーを作成して、事前設定されたセキュリティ ポリシーのメンバーの保護をカスタマイズすることもできます。 詳細については、「 [EOP で送信スパム フィルターを構成する](configure-the-outbound-spam-policy.md)」を参照してください。

- **Microsoft Defender for Office 365 ポリシー**: これらのポリシーは、Microsoft 365 E5またはDefender for Office 365アドオン サブスクリプションを持つ組織にあります。
  - **Standard Preset Security** Policy と Strict Preset Security Policy という名前のDefender for Office 365のフィッシング対策 **ポリシー**。次のものが含まれます。
    - EOP フィッシング対策ポリシーで使用できるのと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - **Standard Preset Security** Policy、**Strict Preset** Security Policy、**および組み込み保護** ポリシーという名前の [セーフ リンク](set-up-safe-links-policies.md) ポリシー。
  - **Standard Preset Security Policy、Strict Preset Security Policy**、**および組み込み保護** ポリシーという名前の [安全な添付ファイル](set-up-safe-attachments-policies.md) **ポリシー**。

EOP 保護は、Defender for Office 365保護とは異なるユーザーに適用することも、同じ受信者に EOP とDefender for Office 365を適用することもできます。

### <a name="policy-settings-in-preset-security-policies"></a>事前設定されたセキュリティ ポリシーのポリシー設定

保護プロファイルでポリシー設定を変更することはできません。 **Standard**、**Strict**、および **組み込みの保護** ポリシー設定の値については、「[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定」を参照](recommended-settings-for-eop-and-office365.md)してください。

> [!NOTE]
> Defender for Office 365保護では、[ユーザー権限借用保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)の送信者と、ドメイン偽装保護の内部ドメインまたは外部ドメイン[を](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)識別する必要があります。
>
> 所有するすべてのドメイン ([承認済みドメイン) は、](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)事前設定されたセキュリティ ポリシーでドメイン偽装保護を自動的に受け取ります。
>
> すべての受信者は、事前設定されたセキュリティ ポリシーで [メールボックス インテリジェンス](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) から偽装保護を自動的に受け取ります。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>事前設定されたセキュリティ ポリシーとその他のポリシーの優先順位

ユーザーに複数のポリシーが適用されている場合、優先度が最も高いものから最も低い優先度まで、次の順序が適用されます。

1. 厳密な事前設定されたセキュリティ ポリシー。
2. 標準の事前設定済みセキュリティ ポリシー。
3. カスタム ポリシー。 カスタム ポリシーは、ポリシーの優先度の値に基づいて適用されます。
4. 安全なリンクと安全な添付ファイルの組み込みの保護プリセットセキュリティ ポリシー。マルウェア対策、スパム対策、フィッシング詐欺対策の既定のポリシー。

言い換えると、 **Strict** 事前設定セキュリティ ポリシーの設定は **、標準** プリセット セキュリティ ポリシーの設定をオーバーライドします。これは、安全なリンクと安全な添付ファイルの **組み込みの保護** プリセット セキュリティ ポリシーの設定と、スパム対策、マルウェア対策、フィッシング詐欺対策の既定のポリシーをオーバーライドするカスタム ポリシーの設定をオーバーライドします。

たとえば、 **Standard Protection** にはセキュリティ設定が存在し、管理者は **Standard 保護** のユーザーを指定します。 **Standard 保護** 設定は、カスタム ポリシーまたは同じユーザーの既定のポリシーでその設定に対して構成されたものではなく、ユーザーに適用されます。

**Standard** または **Strict** の事前設定済みセキュリティ ポリシーをユーザーのサブセットに適用し、特定のニーズを満たすために組織内の他のユーザーにカスタム ポリシーを適用することができます。 この要件を満たすために、次の手順を実行します。

- **Standard** プリセット セキュリティ ポリシーとカスタム ポリシーの設定を **、Strict** プリセット セキュリティ ポリシーの例外として取得する必要があるユーザーを構成します。
- **Standard** プリセット セキュリティ ポリシーの例外としてカスタム ポリシーの設定を取得する必要があるユーザーを構成します。

**組み込みの保護** は、既存の安全なリンクまたは安全な添付ファイル ポリシーの受信者には影響しません。 **Standard Protection**、**Strict Protection**、カスタムセーフ リンク、または安全な添付ファイルポリシーを既に構成している場合、これらのポリシーは **組み込み保護**_の前に__常に_ 適用されるため、既存のプリセットポリシーまたはカスタム ポリシーで既に定義されている受信者には影響しません。

## <a name="assign-preset-security-policies-to-users"></a>事前設定されたセキュリティ ポリシーをユーザーに割り当てる

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 事前設定されたセキュリティ ポリシーを構成するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 事前設定されたセキュリティ ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 の他の機能に必要なアクセス許可 _と_ アクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Microsoft 365 Defender ポータルを使用して、Standard および Strict の事前設定済みセキュリティ ポリシーをユーザーに割り当てる

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**テンプレート** ポリシー] セクション **の [Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **の事前設定されたセキュリティ ポリシー**] に移動します。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

2. **[事前設定されたセキュリティ ポリシー**] ページの [**Standard Protection**] セクションまたは [**Strict protection**] セクションで [**管理**] をクリックします。

3. **[標準保護の適用]** または **[厳格な保護の適用]** ウィザードはポップアップで開始されます。

   [**Exchange Online Protectionの適用**] ページで、[EOP 保護](#policies-in-preset-security-policies)が適用される内部受信者 (受信者の条件) を特定します。
   - **すべての受信者**
   - **特定の受信者**:
     - **Users**
     - **グループ**
     - **ドメイン**

     適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   - **なし**

   - **これらの受信者を除外する**: ポリシーが適用される内部受信者の例外 (受信者の例外) を追加するには、このオプションを選択し、例外を構成します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

   > [!NOTE]
   > Defender for Office 365のない組織では、[**次へ**] をクリックすると、[**校閲**] ページに移動します。 **[校閲**] ページの前の残りの手順/ページは、Defender for Office 365のある組織でのみ使用できます。

4. [**Defender for Office 365保護の適用**] ページで、[Defender for Office 365保護](#policies-in-preset-security-policies)が適用される内部受信者 (受信者の条件) を特定します。

   設定と動作は、前の手順のページ **に適用される EOP 保護** とまったく同じです。

   [ **以前に選択した受信者** ] を選択して、前のページで EOP 保護で選択したものと同じ受信者を使用することもできます。

   完了したら、**[次へ]** をクリックします。

5. [ **偽装保護** ] ページで、[ **次へ**] をクリックします。

6. [ **攻撃者によって偽装されたときにフラグを設定する電子メール アドレスを追加する** ] ページで、 [ユーザー偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)によって保護されている内部および外部の送信者を追加します。

   > [!NOTE]
   > すべての受信者は、事前設定されたセキュリティ ポリシーで [メールボックス インテリジェンス](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) から偽装保護を自動的に受け取ります。

   各エントリは、表示名と電子メール アドレスで構成されます。 ボックスに各値を入力し、[ **追加**] をクリックします。 必要な回数だけこの手順を繰り返します。

   最大 350 人のユーザーを指定でき、複数のポリシーのユーザー偽装保護設定で同じユーザーを指定することはできません。

   リストから既存のエントリを削除するには、 ![偽装保護アイコンからユーザーを削除します。](../../media/m365-cc-sc-remove.png).

   完了したら、**[次へ]** をクリックします。

7. [ **攻撃者による偽装時にフラグを設定するドメインの追加** ] ページで、 [ドメイン偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)によって保護されている内部ドメインと外部ドメインを追加します。

   > [!NOTE]
   > 所有するすべてのドメイン ([承認済みドメイン) は、](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)事前設定されたセキュリティ ポリシーでドメイン偽装保護を自動的に受け取ります。

   指定されたドメイン内のすべての送信者は、ドメイン偽装保護によって保護されます。

   ボックスにドメインを入力し、[ **追加**] をクリックします。 必要な回数だけこの手順を繰り返します。

   リストから既存のエントリを削除するには、エントリを選択し、 ![偽装保護アイコンからドメインを削除します。](../../media/m365-cc-sc-remove.png).

   すべてのフィッシング対策ポリシーでドメイン偽装保護に指定できるドメインの最大数は 50 です。

   完了したら、**[次へ]** をクリックします。

8. [ **偽装としてフラグを設定しない信頼された電子メール アドレスとドメインを追加** する] ページで、偽装保護から除外する送信者の電子メール アドレスとドメインを入力します。 これらの送信者からのメッセージには偽装攻撃のフラグは設定されませんが、送信者は引き続き EOP とDefender for Office 365の他のフィルターによるスキャンの対象となります。

   ボックスにメール アドレスまたはドメインを入力し、[ **追加**] をクリックします。 必要な回数だけこの手順を繰り返します。

   リストから既存のエントリを削除するには、エントリを選択し、 ![偽装保護アイコンに例外を削除します。](../../media/m365-cc-sc-remove.png).

   完了したら、**[次へ]** をクリックします。

9. **[このポリシーの確認と確認**] ページで、選択内容を確認し、[**確認**] をクリックします。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Microsoft 365 Defender ポータルを使用して、Standard および Strict の事前設定済みセキュリティ ポリシーの割り当てを変更する

**Standard Protection** または **Strict Protection** プリセット セキュリティ ポリシーの割り当てを変更する手順は、事前設定 [されたセキュリティ ポリシーをユーザーに最初に割り当てた](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users)場合と同じです。

既存の条件と例外を保持したまま **Standard Protection** または **Strict Protection** の事前設定されたセキュリティ ポリシーを無効にするには、トグルを **[無効]** ![トグル オフにスライドします](../../media/scc-toggle-off.png)。 ポリシーを有効にするには、トグルを [**有効**![] トグルオン](../../media/scc-toggle-on.png)にスライドします。

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Microsoft 365 Defender ポータルを使用して、組み込みの保護プリセット セキュリティ ポリシーの割り当てを変更する

**組み込みの保護** プリセット セキュリティ ポリシーはすべての受信者に割り当てられ、**Standard Protection** または **Strict Protection** プリセット セキュリティ ポリシー、またはカスタムのセーフ リンクまたは安全な添付ファイル ポリシーで定義されている受信者には影響しません。

そのため、通常は **、組み込みの保護** プリセット セキュリティ ポリシーに例外を推奨しません。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**テンプレート** ポリシー] セクション **の [Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **の事前設定されたセキュリティ ポリシー**] に移動します。 **[プリセット セキュリティ ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/presetSecurityPolicies>.

2. **[事前設定されたセキュリティ ポリシー**] ページの [**組み込みの保護**] セクションで [**除外の追加 (推奨されません)]** を選択します。

3. 表示される [ **組み込みの保護から除外** ] ポップアップで、組み込みの安全なリンクと安全な添付ファイル保護から除外されている内部受信者を特定します。
   - **Users**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![組み込みの保護アイコンから除外を削除します。](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   完了したら、**[保存]** をクリックします。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

**Standard Protection** または **Strict Protection** セキュリティ ポリシーがユーザーに正常に割り当てられていることを確認するには、標準保護設定とは異なる標準 **保護** 設定と既定値が異なる **保護** 設定を使用します。

たとえば、スパムとして検出された電子メール (信頼度の高いスパムではない) の場合、メッセージが **Standard 保護** ユーザーの迷惑メール Email フォルダーに配信され、**Strict Protection** ユーザー用に検疫されていることを確認します。

または、[一括メール](bulk-complaint-level-values.md)の場合は、BCL 値 6 以上が **Standard 保護** ユーザーの迷惑メール Email フォルダーにメッセージを配信し、BCL 値 4 以上が **Strict Protection** ユーザーのメッセージを検疫することを確認します。

## <a name="preset-security-policies-in-exchange-online-powershell"></a>Exchange Online PowerShell の事前設定済みセキュリティ ポリシー

PowerShell では、事前設定されたセキュリティ ポリシーは次の要素で構成されます。

- **個々のセキュリティ ポリシー**: たとえば、マルウェア対策ポリシー、スパム対策ポリシー、フィッシング対策ポリシー、セーフ リンク ポリシー、安全な添付ファイル ポリシーなどです。

  > [!WARNING]
  > 事前設定されたセキュリティ ポリシーに関連付けられている個々のセキュリティ ポリシーを作成、変更、または削除しないでください。 Standard または Strict の事前設定済みセキュリティ ポリシーの個々のセキュリティ ポリシーを作成するためにサポートされている唯一の方法は、Microsoft 365 Defender ポータルで初めて事前設定されたセキュリティ ポリシーを有効にすることです。

- **ルール**: Standard プリセット セキュリティ ポリシー、Strict プリセット セキュリティ ポリシー、および組み込み保護プリセット セキュリティ ポリシーの個別のルールは、ポリシーの受信者の条件と例外を定義します (ポリシーの保護が適用される受信者を識別します)。

  Standard および Strict の事前設定済みセキュリティ ポリシーの場合、これらのルールは、Microsoft 365 Defender ポータルで事前設定されたセキュリティ ポリシーを初めて有効にするときに作成されます。 事前設定されたセキュリティ ポリシーを有効にしたことがない場合は、関連付けられているルールは存在しません。 その後、事前設定されたセキュリティ ポリシーをオフにしても、関連付けられているルールは削除されません。

  組み込みの保護プリセット セキュリティ ポリシーには、ポリシーの既定の安全なリンクと安全な添付ファイルの保護に対する例外を制御する 1 つの規則があります。

  Standard および Strict の事前設定済みセキュリティ ポリシーには、次の規則があります。

  - **Exchange Online Protection (EOP) 保護の規則**: Standard Preset セキュリティ ポリシーの規則と、ポリシー内の EOP 保護 (マルウェア対策、スパム対策、フィッシング詐欺対策) が適用されるユーザー (EOP 保護の受信者の条件と例外) を制御する、標準プリセット セキュリティ ポリシーの規則。
  - **Defender for Office 365保護の規則**: Standard Preset セキュリティ ポリシーの規則と、ポリシーのDefender for Office 365保護 (安全なリンクと安全な添付ファイル) が適用されるユーザー (受信者の条件と例外) を制御する、標準プリセット セキュリティ ポリシーの規則。Defender for Office 365保護)。

  Standard および Strict の事前設定済みセキュリティ ポリシーのルールでは、ポリシーに関連付けられているルールを有効または無効にすることで、事前設定されたセキュリティ ポリシーを有効または無効にすることもできます。

  事前設定されたセキュリティ ポリシーのルールは、個々のセキュリティ ポリシー ( **Get-AntiPhishRule** など) で動作する通常のルール コマンドレットでは使用できません。 代わりに、次のコマンドレットが必要です。

  - 組み込みの保護プリセット セキュリティ ポリシー: **\*-ATPBuiltInProtectionRule** コマンドレット。
  - 標準および厳密な事前設定済みセキュリティ ポリシー: **\*-EOPProtectionPolicyRule** コマンドレットと **\*-ATPProtectionPolicyRule** コマンドレット。

次のセクションでは、 **サポートされているシナリオ** でこれらのコマンドレットを使用する方法について説明します。

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

### <a name="use-powershell-to-view-individual-security-policies-for-preset-security-policies"></a>PowerShell を使用して、事前設定されたセキュリティ ポリシーの個々のセキュリティ ポリシーを表示する

Microsoft 365 Defender ポータルで Standard プリセット セキュリティ ポリシーまたは Strict 事前設定セキュリティ ポリシーをオンにしていない場合は、事前設定されたセキュリティ ポリシーに関連付けられているセキュリティ ポリシーが存在しないことを忘れないでください。

> [!WARNING]
> 事前設定されたセキュリティ ポリシーに関連付けられている個々のセキュリティ ポリシーを作成、変更、または削除しないでください。 Standard または Strict の事前設定済みセキュリティ ポリシーの個々のセキュリティ ポリシーを作成するためにサポートされている唯一の方法は、Microsoft 365 Defender ポータルで初めて事前設定されたセキュリティ ポリシーを有効にすることです。

- **組み込みの保護プリセット セキュリティ ポリシー**: 関連付けられているポリシーには、保護ポリシーBuilt-In名前が付けられます。 IsBuiltInProtection プロパティの値は、これらのポリシーに対して True です。

  組み込みの保護プリセット セキュリティ ポリシーの個々のセキュリティ ポリシーを表示するには、次のコマンドを実行します。

  ```powershell
  Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy -Identity "Built-In Protection Policy" | Format-List; Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Links policy",("-"*79);Get-SafeLinksPolicy -Identity "Built-In Protection Policy" | Format-List
  ```

- **標準の事前設定済みセキュリティ ポリシー**: 関連付けられたポリシーには名前が付けられます `Standard Preset Security Policy<13-digit number>`。 たとえば、「 `Standard Preset Security Policy1622650008019` 」のように入力します。 RecommendPolicyType プロパティの値は Standard です。

  - **Defender for Microsoft 365 を使用していない組織**:

    Defender for Microsoft 365 を使用していない組織の Standard プリセット セキュリティ ポリシーの個々のセキュリティ ポリシーを表示するには、次のコマンドを実行します。

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

  - **Defender for Microsoft 365 を使用している組織**:

    Defender for Microsoft 365 を使用している組織の Standard プリセット セキュリティ ポリシーの個々のセキュリティ ポリシーを表示するには、次のコマンドを実行します。

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

- **厳密な事前設定済みセキュリティ ポリシー**: 関連付けられているポリシーには名前が付けられます `Strict Preset Security Policy<13-digit number>`。 たとえば、「 `Strict Preset Security Policy1642034872546` 」のように入力します。 RecommendPolicyType プロパティの値は Strict です。

  - **Defender for Microsoft 365 を使用していない組織**:

    - Defender for Microsoft 365 を使用していない組織の Strict プリセット セキュリティ ポリシーの個々のセキュリティ ポリシーを表示するには、次のコマンドを実行します。

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
      ```

  - **Defender for Microsoft 365 を使用している組織**:

    - Defender for Microsoft 365 を使用している組織の Strict プリセット セキュリティ ポリシーの個々のセキュリティ ポリシーを表示するには、次のコマンドを実行します。

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
    ```

### <a name="use-powershell-to-view-rules-for-preset-security-policies"></a>PowerShell を使用して、事前設定されたセキュリティ ポリシーのルールを表示する

Microsoft 365 Defender ポータルで Standard プリセット セキュリティ ポリシーまたは Strict 事前設定セキュリティ ポリシーを一度も有効にしていない場合は、それらのポリシーに関連するルールが存在しないことを忘れないでください。

- **組み込みの保護プリセット セキュリティ ポリシー**: 関連付けられたルールは ATP Built-In Protection Rule という名前です。

  組み込みの保護プリセット セキュリティ ポリシーに関連付けられているルールを表示するには、次のコマンドを実行します。

  ```powershell
  Get-ATPBuiltInProtectionRule
  ```

  構文とパラメーターの詳細については、「 [Get-ATPBuiltInProtectionRule](/powershell/module/exchange/get-atpbuiltinprotectionrule)」を参照してください。

- **Standard プリセット セキュリティ ポリシー**: 関連付けられたルールには、Standard Preset Security Policy という名前が付けられます。

  次のコマンドを使用して、Standard プリセット セキュリティ ポリシーに関連付けられているルールを表示します。

  - Standard プリセット セキュリティ ポリシーで EOP 保護に関連付けられているルールを表示するには、次のコマンドを実行します。

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - Standard プリセット セキュリティ ポリシーでDefender for Office 365保護に関連付けられているルールを表示するには、次のコマンドを実行します。

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - 両方のルールを同時に表示するには、次のコマンドを実行します。

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Standard preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

- **厳密な事前設定済みセキュリティ ポリシー**: 関連付けられているルールには、Strict Preset Security Policy という名前が付けられます。

  次のコマンドを使用して、Strict プリセット セキュリティ ポリシーに関連付けられているルールを表示します。

  - Strict プリセット セキュリティ ポリシーで EOP 保護に関連付けられているルールを表示するには、次のコマンドを実行します。

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - Strict プリセット セキュリティ ポリシーでDefender for Office 365保護に関連付けられているルールを表示するには、次のコマンドを実行します。

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - 両方のルールを同時に表示するには、次のコマンドを実行します。

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Strict preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

構文とパラメーターの詳細については、「 [Get-EOPProtectionPolicyRule](/powershell/module/exchange/get-eopprotectionpolicyrule) 」および「 [Get-ATPProtectionPolicyRule](/powershell/module/exchange/get-atpprotectionpolicyrule)」を参照してください。

### <a name="use-powershell-to-turn-on-or-turn-off-preset-security-policies"></a>PowerShell を使用して、事前設定されたセキュリティ ポリシーを有効または無効にする

前述のように、Standard または Strict の事前設定済みセキュリティ ポリシーを有効または無効にするには、ポリシーに関連付けられているルールを有効または無効にします。 ルールの State プロパティ値は、ルールが有効か無効かを示します。

組織にDefender for Office 365しているかどうかに応じて、1 つのルール (EOP 保護のルール) または 2 つのルール (EOP 保護の 1 つのルールと、Defender for Office 365保護用の 1 つのルール) を有効または無効にして、事前設定されたセキュリティ ポリシーを有効または無効にする必要がある場合があります。

- **標準の事前設定されたセキュリティ ポリシー**:

  - **Defender for Office 365のない組織**:

    - Defender for Office 365のない組織では、次のコマンドを実行して、Standard プリセット ポリシーのルールが現在有効か無効かを判断します。

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - 次のコマンドを実行して、Standard プリセット セキュリティ ポリシーが有効になっている場合はオフにします。

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - 次のコマンドを実行して、Standard プリセット セキュリティ ポリシーがオフになっている場合はオンにします。

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

  - **Defender for Office 365を持つ組織**:

    - Defender for Office 365を使用している組織では、次のコマンドを実行して、Standard プリセット ポリシーのルールが現在有効か無効かを判断します。

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Standard preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - 次のコマンドを実行して、Standard プリセット セキュリティ ポリシーが有効になっている場合はオフにします。

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - 次のコマンドを実行して、Standard プリセット セキュリティ ポリシーがオフになっている場合はオンにします。

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

- **厳密な事前設定済みセキュリティ ポリシー**:

  - **Defender for Office 365のない組織**:

    - Defender for Office 365を使用している組織では、次のコマンドを実行して、Strict プリセット ポリシーのルールが現在有効か無効かを判断します。

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - 次のコマンドを実行して、Strict プリセット セキュリティ ポリシーが有効になっている場合は無効にします。

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - 次のコマンドを実行して、Strict プリセット セキュリティ ポリシーがオフになっている場合に有効にします。

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

  - **Defender for Office 365を持つ組織**:

    - Defender for Office 365を使用している組織では、次のコマンドを実行して、Strict プリセット ポリシーのルールが現在有効か無効かを判断します。

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Strict preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - 次のコマンドを実行して、Strict プリセット セキュリティ ポリシーが有効になっている場合は無効にします。

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - 次のコマンドを実行して、Strict プリセット セキュリティ ポリシーがオフになっている場合に有効にします。

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

構文とパラメーターの詳細については、「 [Enable-EOPProtectionPolicyRule](/powershell/module/exchange/enable-eopprotectionpolicyrule)、 [Enable-ATPProtectionPolicyRule](/powershell/module/exchange/enable-atpprotectionpolicyrule)、 [Disable-EOPProtectionPolicyRule](/powershell/module/exchange/disable-eopprotectionpolicyrule)、 [Disable-ATPProtectionPolicyRule](/powershell/module/exchange/disable-atpprotectionpolicyrule)」を参照してください。

### <a name="use-powershell-to-specify-recipient-conditions-and-exceptions-for-preset-security-policies"></a>PowerShell を使用して、事前設定されたセキュリティ ポリシーの受信者の条件と例外を指定する

> [!IMPORTANT]
  > 複数の異なる種類の条件や例外は加算されません。包括的です。 事前設定されたセキュリティ ポリシーは、指定 _されたすべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
  >
  > - 受信者は次のとおりです: romain@contoso.com
  > - 受信者が次のメンバーの場合: Executive
  >
  > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
  >
  > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

組み込みの保護プリセット セキュリティ ポリシーでは、受信者の例外のみを指定できます。 すべての例外パラメーター値が空の場合 (`$null`)、ポリシーに例外はありません。

Standard および Strict の事前設定済みセキュリティ ポリシーでは、EOP 保護とDefender for Office 365保護の受信者の条件と例外を指定できます。 すべての条件と例外パラメーターの値が空 (`$null`) の場合、Standard または Strict の事前設定済みセキュリティ ポリシーに対する受信者の条件や例外はありません。

既定のセキュリティ ポリシーに受信者の条件や例外が適用されていない場合でも、ポリシーがすべての受信者に適用されるかどうかは、この記事で前述したように [、ポリシーの優先順位](#order-of-precedence-for-preset-security-policies-and-other-policies) によって異なります。

- **組み込みの保護プリセット セキュリティ ポリシー**:

  次の構文を使用してください。

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null>
  ```

  この例では、組み込みの保護プリセット セキュリティ ポリシーからすべての受信者例外を削除します。

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs $null -ExceptIfSentTo $null -ExceptIfSentToMemberOf $null
  ```

  構文とパラメーターの詳細については、「 [Set-ATPBuiltInProtectionRule](/powershell/module/exchange/set-atpbuiltinprotectionrule)」を参照してください。

- **Standard または Strict の事前設定済みセキュリティ ポリシー**

  次の構文を使用してください。

  ```powershell
  <Set-EOPProtectionPolicyRule | SetAtpProtectionPolicyRule> -Identity "<Standard Preset Security Policy | Strict Preset Security Policy>" -SentTo <"user1","user2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -SentToMemberOf <"group1","group2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null> -RecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null>
  ```

  この例では、Executives という名前の配布グループのメンバーに対して、Standard プリセット セキュリティ ポリシーの EOP 保護からの例外を構成します。

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" -ExceptIfSentToMemberOf Executives
  ```

  この例では、指定されたセキュリティ操作 (SecOps) メールボックスの Strict 事前設定済みセキュリティで、Defender for Office 365保護からの例外を構成します。

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" -ExceptIfSentTo "SecOps1","SecOps2"
  ```

  構文とパラメーターの詳細については、「 [Set-EOPProtectionPolicyRule](/powershell/module/exchange/set-eopprotectionpolicyrule) 」および [「Set-ATPProtectionPolicyRule](/powershell/module/exchange/Set-atpprotectionpolicyrule)」を参照してください。
