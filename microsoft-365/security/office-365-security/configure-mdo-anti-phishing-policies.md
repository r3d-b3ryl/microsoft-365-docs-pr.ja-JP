---
title: 詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。
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
description: 管理者は、Microsoft Defender for Office 365を使用している組織で使用できる高度なフィッシング対策ポリシーを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b641fe1fb4de8dcb7d7ec299a0e8b19a064efad
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084127"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護するのに役立ちます。 Exchange Online Protection (EOP) のフィッシング対策ポリシーとMicrosoft Defender for Office 365でのフィッシング対策ポリシーの違いの詳細については、「[フィッシング対策の保護」を](anti-phishing-protection.md)参照してください。

管理者は、既定のフィッシング対策ポリシーを表示、編集、構成 (ただし削除) することはできません。 粒度を高めるために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

フィッシング対策ポリシーは、Microsoft 365 Defender ポータルまたは powerShell Exchange Online Defender for Office 365で構成できます。

Exchange Online Protectionで使用できるフィッシング対策ポリシー (つまり、Defender for Office 365のない組織) の構成の詳細については、「[EOP でのフィッシング対策ポリシーの構成](configure-anti-phishing-policies-eop.md)」を参照してください。

フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール: フィッシング対策** ポリシーの優先度フィルターと受信者フィルター (ポリシーが適用されるユーザー) を指定します。

Microsoft 365 Defender ポータルでフィッシング対策ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。

- ポリシーを作成すると、実際には、両方に同じ名前を使用して、フィッシング対策ルールと関連するフィッシング対策ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。 その他のすべての設定では、関連するフィッシング対策ポリシーが変更されます。
- ポリシーを削除すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが削除されます。

Exchange Online PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半の「[Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する](#use-exchange-online-powershell-to-configure-anti-phishing-policies)」セクションを参照してください。

すべてのDefender for Office 365組織には、次のプロパティを持つフィッシング対策ポリシー Office 365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。

- ポリシーに関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

Defender for Office 365でのフィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用されるより厳しい設定でカスタムフィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - フィッシング対策ポリシーを追加、変更、削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - フィッシング対策ポリシーへの読み取り専用アクセスの場合は、 **グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループ <sup>\*</sup>のメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- Defender for Office 365のフィッシング対策ポリシーの推奨設定については、「[Defender for Office 365設定のフィッシング対策ポリシー](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)」を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- フィルタリング パイプラインでフィッシング対策ポリシーが適用される場所については、「 [電子メール保護の順序と優先順位」を](how-policies-and-protections-are-combined.md)参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Microsoft 365 Defender ポータルを使用してフィッシング対策ポリシーを作成する

Microsoft 365 Defender ポータルでカスタムフィッシング対策ポリシーを作成すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが同時に作成され、両方に同じ名前が使用されます。

1. Microsoft 365 Defender ポータルの [ポリシー **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

2. [ **フィッシング対策** ] ページで、[作成] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. ポリシー ウィザードが開きます。 [ **ポリシー名** ] ページで、次の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 
     - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
     - 指定した Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件の複数の値は、OR ロジックを使用します (たとえば _\<recipient1\>_ または _\<recipient2\>_)。異なる条件では AND ロジックを使用します (たとえば _\<recipient1\>_ および _\<member of group 1\>_)。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   > [!IMPORTANT]
   > 複数の異なる種類の条件や例外は加算されません。包括的です。 ポリシーは、指定された _すべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
   >
   > - 受信者は次のとおりです: romain@contoso.com
   > - 受信者が次のメンバーの場合: Executive
   >
   > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
   >
   > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

   完了したら、**[次へ]** をクリックします。

5. 表示される [ **フィッシングのしきい値&保護** ] ページで、次の設定を構成します。

   - **フィッシングメールのしきい値**: スライダーを使用して、次のいずれかの値を選択します。
     - **1 - Standard** (既定値です)。
     - **2 - アグレッシブ**
     - **3 - より積極的**
     - **4 - 最も攻撃的**

     詳細については、「[Microsoft Defender for Office 365のフィッシング対策ポリシーの高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。

   - **偽装**: これらの設定は、受信メッセージの送信元アドレスで (個別またはドメイン別に) 検索する特定の送信者を識別するポリシーの条件です。 詳細については、「[Microsoft Defender for Office 365のフィッシング対策ポリシーの偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。

     > [!NOTE]
     >
     > - 各フィッシング対策ポリシーでは、最大 350 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。 複数のポリシーで同じ保護されたユーザーを指定することはできません。
     > - 送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。 送信者と受信者が電子メールで通信したことがない場合、メッセージは偽装の試行として識別されます。

     - **ユーザーの保護を有効にする**: 既定値はオフです (選択されていません)。 オンにするには、チェック ボックスをオンにし、表示される **[送信者の管理] (nn)** リンクをクリックします。

       表示される **偽装保護ポップアップの [送信者の管理** ] で、次の手順を実行します。

       - **内部送信者**: [内部の追加] アイコンをクリック ![します。](../../media/m365-cc-sc-add-internal-icon.png) **内部を選択します**。 表示される [ **内部送信者の追加]** ポップアップで、ボックスをクリックし、一覧から内部ユーザーを選択します。 リストをフィルター処理するには、ユーザーを入力し、結果からユーザーを選択します。 ほとんどの識別子 (名前、表示名、エイリアス、電子メール アドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。

         必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

         完了したら、[**追加**] をクリックします。

       - **外部送信者**: [外部の追加] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **外部を選択します**。 表示される [ **外部送信者の追加]** ポップアップで、[名前の **追加** ] ボックスに表示名を入力し、[メール アドレスの **追加]** ボックスにメール アドレスを入力し、[ **追加**] をクリックします。

         必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

         完了したら、[**追加**] をクリックします。

       **偽装ポップアップの [送信者の管理**] に戻り、一覧から 1 つ以上のエントリを選択してエントリを削除できます。 検索アイコンを使用してエントリを ![検索できます。](../../media/m365-cc-sc-create-icon.png) **検索** ボックス。

       少なくとも 1 つのエントリを選択すると、[選択したユーザーの ![削除] アイコンが表示されます。](../../media/m365-cc-sc-remove-selected-users-icon.png) **[選択したユーザーの削除]** アイコンが表示され、選択したエントリを削除するために使用できます。

       完了したら、[**完了**] をクリックします。

     - **保護するドメインを有効にする**: 既定値はオフです (選択されていません)。 オンにするには、チェック ボックスをオンにし、次に表示される設定のいずれかまたは両方を構成します。
       - **自分が所有するドメインを含める**: この設定を有効にするには、チェック ボックスをオンにします。 所有しているドメインを表示するには、[ **自分のドメインの表示**] をクリックします。
       - **カスタム ドメインを含める**: この設定をオンにするには、チェック ボックスをオンにし、表示される **[管理] (nn) カスタム ドメインの** リンクをクリックします。 表示される **偽装保護のカスタム ドメインの管理** ポップアップで、[ドメインの追加] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ドメインを追加する**。

         表示される [ **カスタム ドメインの追加]** ポップアップで、[ **ドメイン** ] ボックスをクリックして値を入力し、Enter キーを押すか、ボックスの下に表示される値を選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

         完了したら、[**ドメインの追加**] をクリックします。

         > [!NOTE]
         > すべてのフィッシング対策ポリシーには、最大 50 個のドメインを含めることができます。

       **偽装ポップアップの [カスタム ドメインの管理**] に戻り、一覧から 1 つ以上のエントリを選択してエントリを削除できます。 検索アイコンを使用してエントリを ![検索できます。](../../media/m365-cc-sc-create-icon.png) **検索** ボックス。

       少なくとも 1 つのエントリを選択すると、[ドメインの削除] ![アイコンが表示されます。](../../media/m365-cc-sc-delete-icon.png) **[削除]** アイコンが表示され、選択したエントリを削除するために使用できます。

   - **信頼できる送信者とドメインを追加する: [信頼された送信者の****管理] と [ドメイン**] をクリックして、ポリシーの偽装保護の例外を指定します。 表示される **偽装保護ポップアップのカスタム ドメインの管理** で、次の設定を構成します。
      - **送信者**: [**送信者**] タブが選択されていることを確認し、[送信者の追加] アイコンをクリックします![](../../media/m365-cc-sc-create-icon.png)。 表示される [ **信頼できる送信者の追加]** ポップアップで、ボックスにメール アドレスを入力し、[ **追加**] をクリックします。 必要な回数だけこの手順を繰り返します。 既存のエントリを削除するには、エントリの [削除] アイコン](../../media/m365-cc-sc-close-icon.png)をクリックします![。

        完了したら、**[追加]** をクリックします。

      - **ドメイン**: [**ドメイン**] タブを選択し、[ドメインの追加] アイコンをクリックします![](../../media/m365-cc-sc-create-icon.png)。

        表示された [ **信頼されたドメインの追加]** ポップアップで、[ **ドメイン** ] ボックスをクリックし、値を入力して Enter キーを押すか、ボックスの下に表示される値を選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

        完了したら、**[追加]** をクリックします。

     **偽装ポップアップの [カスタム ドメインの管理**] に戻り、一覧から 1 つ以上のエントリを選択して、[**送信者**] タブと **[ドメイン]** タブからエントリを削除できます。 検索アイコンを使用してエントリを ![検索できます。](../../media/m365-cc-sc-create-icon.png) **検索** ボックス。

     少なくとも 1 つのエントリを選択すると、[ **削除** ] アイコンが表示され、選択したエントリを削除するために使用できます。

     完了したら、[**完了**] をクリックします。

     > [!NOTE]
     > 送信者エントリとドメイン エントリの最大数は 1024 です。

   - **メールボックス インテリジェンスを有効にする**: 既定値はオン (選択済み) であり、そのままにしておくことをお勧めします。 オフにするには、チェック ボックスをオフにします。

     - **インテリジェンス ベースの偽装保護を有効にする**: この設定は、[ **メールボックス インテリジェンスを有効にする]** がオン (選択済み) の場合にのみ使用できます。 この設定により、メールボックス インテリジェンスは、偽装試行として識別されるメッセージに対してアクションを実行できます。 次のページで、[ **メールボックス インテリジェンスが偽装されたユーザーを検出した場合** ] 設定で実行するアクションを指定します。

       チェック ボックスをオンにして、この設定をオンにすることをお勧めします。 この設定をオフにするには、チェック ボックスをオフにします。

   - **スプーフィング**: このセクションでは、[ **スプーフィング インテリジェンスを有効にする** ] チェック ボックスを使用して、スプーフィング インテリジェンスをオンまたはオフにします。 既定値はオン (選択済み) であり、そのままにしておくことをお勧めします。 次のページの [メッセージがスプーフィングとして検出された場合] 設定で、ブロック **されたスプーフィングされた** 送信者からのメッセージを実行するアクションを指定します。

     スプーフィング インテリジェンスを無効にするには、チェック ボックスをオフにします。

     > [!NOTE]
     > MX レコードが Microsoft 365 を指していない場合は、スプーフィング対策保護を無効にする必要はありません。代わりに、コネクタの拡張フィルター処理を有効にします。 手順については、「Exchange Onlineの[コネクタの拡張フィルター処理](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

   完了したら、**[次へ]** をクリックします。

6. **[アクション]** ページが表示されたら、次の設定を構成します。

   - **メッセージ アクション**: このセクションで次のアクションを構成します。
     - **メッセージが偽装ユーザーとして検出された場合**: この設定は、前のページで [ **ユーザーの保護を有効にする]** を選択した場合にのみ使用できます。 送信者が前のページで指定した保護されたユーザーの 1 つであるメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **受信者の迷惑メール Email フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[ **検疫ポリシーの適用** ] ボックスが表示され、ユーザー偽装保護によって検疫されたメッセージに適用される検疫ポリシーが選択されます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         空白の **[検疫ポリシーの適用** ] の値は、既定の検疫ポリシーが使用されていることを意味します (ユーザーの偽装検出には DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。
  
       - **メッセージを配信し、Bcc 行に他のアドレスを追加する**
       - **メッセージが配信される前にメッセージを削除する**

     - **メッセージが偽装されたドメインとして検出された場合**: この設定は、前のページで [ **ドメインを保護するドメインを有効にする]** を選択した場合にのみ使用できます。 送信者の電子メール アドレスが前のページで指定した保護されたドメインのいずれかに含まれているメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **受信者の迷惑メール Email フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[ **検疫ポリシーの適用** ] ボックスが表示され、ドメイン偽装保護によって検疫されたメッセージに適用される検疫ポリシーが選択されます。

         空白の **[検疫ポリシーの適用** ] の値は、既定の検疫ポリシーが使用されていることを意味します (ドメイン偽装検出では DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

       - **メッセージを配信し、Bcc 行に他のアドレスを追加する**
       - **メッセージが配信される前にメッセージを削除する**

     - **メールボックス インテリジェンスで偽装されたユーザーが検出された場合**: この設定は、前のページで [ **偽装保護のインテリジェンスを有効にする]** を選択した場合にのみ使用できます。 メールボックス インテリジェンスによる偽装試行として識別されたメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **受信者の迷惑メール Email フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[ **検疫ポリシーの適用** ] ボックスが表示され、メールボックス インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーが選択されます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         空白の **[検疫ポリシーの適用** ] の値は、既定の検疫ポリシーが使用されていることを意味します (メールボックス インテリジェンス検出には DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

       - **メッセージを配信し、Bcc 行に他のアドレスを追加する**
       - **メッセージが配信される前にメッセージを削除する**

     - **メッセージがスプーフィングとして検出された場合**: この設定は、前のページで [ **スプーフィング インテリジェンスを有効にする]** を選択した場合にのみ使用できます。 ブロックされたスプーフィングされた送信者からのメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **受信者の迷惑メール Email フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[ **検疫ポリシーの適用** ] ボックスが表示され、スプーフィング インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーが選択されます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         空白の **[検疫ポリシーの適用** ] の値は、既定の検疫ポリシーが使用されていることを意味します (スプーフィング インテリジェンス検出には DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

   - **安全に関するヒント&インジケーター**: 次の設定を構成します。
     - **最初の連絡先の安全に関するヒントを表示** する: 詳細については、 [最初の連絡先の安全に関するヒントに関するページを](set-up-anti-phishing-policies.md#first-contact-safety-tip)参照してください。
     - **ユーザー権限借用の安全性に関するヒントを表示** する: この設定は、前のページで [ **ユーザーの保護を有効にする]** を選択した場合にのみ使用できます。
     - **ドメイン偽装の安全性に関するヒントを表示** する: この設定は、前のページで [ **ドメインを保護する] を** 選択した場合にのみ使用できます。
     - **ユーザー権限借用の異常な文字の安全性のヒントを表示する** この設定は、前のページで [ **ユーザーの保護を有効にする]** または **[ドメインの保護を有効にする]** を選択した場合にのみ使用できます。
     - **スプーフィングの認証されていない送信者の表示 (?)** : この設定は、前のページで [ **スプーフィング インテリジェンスを有効にする]** を選択した場合にのみ使用できます。 メッセージが SPF または DKIM チェックに合格せず、メッセージが DMARC または [複合認証](email-validation-and-authentication.md#composite-authentication)に合格しない場合、Outlook の [差 **出** 人] ボックスで送信者の写真に疑問符 (?) を追加します。
     - **"via" タグを表示** する: この設定は、前のページで **[スプーフィング インテリジェンスを有効にする]** を選択した場合にのみ使用できます。 DKIM 署名または **MAIL FROM** アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で chris@contoso.com) を追加します。 既定値はオン (選択) です。 オフにするには、チェック ボックスをオフにします。

     設定を有効にするには、チェック ボックスをオンにします。 オフにするには、チェック ボックスをオフにします。

   完了したら、**[次へ]** をクリックします。

7. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

8. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Microsoft 365 Defender ポータルを使用してフィッシング対策ポリシーを表示する

1. Microsoft 365 Defender ポータルで、[ポリシー] セクション **の [Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策****]** に移動します。

2. [ **フィッシング対策** ] ページで、フィッシング対策ポリシーの一覧に次のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **最終更新日時**

3. ポリシーの名前をクリックして選択すると、ポリシー設定がポップアウトで表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Microsoft 365 Defender ポータルを使用してフィッシング対策ポリシーを変更する

1. Microsoft 365 Defender ポータルの [ポリシー **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

2. [ **フィッシング対策** ] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の前半の「[Microsoft 365 Defender ポータルを使用してフィッシング対策ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)」セクションを参照してください。

   既定のフィッシング対策ポリシーでは、[ **ユーザー]、[グループ]、[ドメイン** ] セクションは使用できず (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションをご覧ください。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーを有効または無効にする

既定のフィッシング対策ポリシーを無効にすることはできません。

1. Microsoft 365 Defender ポータルの [ポリシー **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

2. [ **フィッシング対策** ] ページで、名前をクリックして、一覧からカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーの優先度を設定する

既定では、フィッシング対策ポリシーには、作成された順序に基づく優先順位が与えられます (新しいポリシーは古いポリシーよりも優先順位が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- Microsoft 365 Defender ポータルでは、フィッシング対策ポリシーを作成した後でのみ、優先順位を変更できます。 PowerShell では、フィッシング対策ルールを作成するときに既定の優先度をオーバーライドできます (既存のルールの優先度に影響を与える可能性があります)。
- フィッシング対策ポリシーは、表示された順序で処理されます (最初のポリシーの **優先度** の値は 0 です)。 既定のフィッシング対策ポリシーの優先度は **[最低]** で、変更することはできません。

1. Microsoft 365 Defender ポータルの [ポリシー **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

2. [ **フィッシング対策** ] ページで、名前をクリックして、一覧からカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - **優先度** の値が **0** のポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。
   - **優先度** 値が最低のポリシー (例: **3**) では、**[優先度を下げる]** オプションのみ利用可能です。
   - 3 つ以上のポリシーがある場合、優先度の値が最も高いポリシーと最も低いポリシーの間では、**[優先度を上げる]** と **[優先度を下げる]** の両方のオプションが利用可能です。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Microsoft 365 Defender ポータルを使用してカスタムフィッシング対策ポリシーを削除する

Microsoft 365 Defender ポータルを使用してカスタムフィッシング対策ポリシーを削除すると、フィッシング対策ルールと対応するフィッシング対策ポリシーの両方が削除されます。 既定のフィッシング対策ポリシーを削除することはできません。

1. Microsoft 365 Defender ポータルの [ポリシー **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。 **[フィッシング対策**] ページに直接移動するには、 <https://security.microsoft.com/antiphishing>.

2. [ **フィッシング対策** ] ページで、ポリシーの名前をクリックして、一覧からカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \> ![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png) **[ポリシーの削除]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する

前述のように、スパム対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。

Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。 -AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを **\*管理し、-AntiPhishRule** コマンドレットを **\*** 使用してフィッシング対策ルールを管理します。

- PowerShell では、まずフィッシング対策ポリシーを作成し、次に、ルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除しても、対応するフィッシング対策ルールは自動的に削除されません。また、その逆も同様です。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でのフィッシング対策ポリシーの作成は、2 段階のプロセスです。

1. フィッシング対策ポリシーを作成します。
2. ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注**:

- 新しいフィッシング対策ルールを作成し、関連付けられていない既存のフィッシング対策ポリシーを割り当てることができます。 フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けることはできません。
- ポリシーの作成後まで、Microsoft 365 Defender ポータルでは使用できない PowerShell の新しいフィッシング対策ポリシーで、次の設定を構成できます。
  - 無効として新しいポリシーを作成します (**New-AntiPhishRule コマンドレットで**_有効)。_ `$false`
  - **New-AntiPhishRule** コマンドレットの作成時のポリシーの _優先度 (優先度__\<Number\>_) を設定します。
- PowerShell で作成した新しいフィッシング対策ポリシーは、フィッシング対策ルールにポリシーを割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- ポリシーが有効になっています ( _Enabled_ パラメーターは使用されておらず、既定値は `$true`有効です)。
- 説明は、研究部門のポリシーです。
- スプーフィング検出の既定のアクションを検疫に変更し、検疫されたメッセージに既定の [検疫ポリシー](quarantine-policies.md) を使用します ( _SpoofQuarantineTag_ パラメーターは使用していません)。
- 承認済みのすべてのドメインの組織ドメイン保護と、fabrikam.com の対象ドメイン保護を有効にします。
- ドメイン偽装検出のアクションとして検疫を指定し、検疫されたメッセージに既定の [検疫ポリシー](quarantine-policies.md) を使用します ( _TargetedDomainQuarantineTag_ パラメーターは使用していません)。
- 偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。
- ユーザー偽装検出のアクションとして検疫を指定し、検疫されたメッセージに既定の [検疫ポリシー](quarantine-policies.md) を使用します ( _TargetedUserQuarantineTag_ パラメーターは使用していません)。
- メールボックス インテリジェンス (_EnableMailboxIntelligence_) を有効にし、メールボックス インテリジェンス保護がメッセージに対してアクションを実行できるようにします (_EnableMailboxIntelligenceProtection_)、検出されたメッセージのアクションとして検疫を指定し、検疫されたメッセージの既定の [検疫ポリシー](quarantine-policies.md) を使用します ( _MailboxIntelligenceQuarantineTag_ パラメーターは使用していません)。
- すべての安全に関するヒントを有効にします。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

構文とパラメーターの詳細については、「[New-MalwareFilterRule](/powershell/module/exchange/New-AntiPhishPolicy)」を参照してください。

> [!NOTE]
> フィッシング対策ポリシーで使用する [検疫ポリシー](quarantine-policies.md) を指定する詳細な手順については、「 [PowerShell を使用してフィッシング対策ポリシーで検疫ポリシーを指定する](quarantine-policies.md#anti-phishing-policies)」を参照してください。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシング対策ルールを作成する

フィッシング対策ルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件で Research Department という名前のフィッシング対策ルールを作成します。

- このルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられています。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- _Priority_ パラメーターを使用していないため、既定の優先度が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文とパラメーターの詳細については、「 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)」を参照してください。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを表示する

既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要一覧を返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文とパラメーターの詳細については、「 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを表示する

既存のフィッシング対策ルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共に、すべてのフィッシング詐欺対策ルールの概要リストを返します。

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

構文とパラメーターの詳細については、「 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを変更する

次の項目以外は、この記事の「手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する」セクションで説明したように、 [PowerShell でフィッシング対策ポリシーを](#step-1-use-powershell-to-create-an-anti-phish-policy) 変更する場合と同じ設定を使用できます。

- 指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に **優先度が低** く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更した場合にのみ使用できます。

- フィッシング対策ポリシーの名前を変更することはできません ( **Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターがありません)。 Microsoft 365 Defender ポータルでフィッシング対策ポリシーの名前を変更する場合は、フィッシング対策 _ルール_ の名前を変更するだけです。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「[Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)」を参照してください。

> [!NOTE]
> フィッシング対策ポリシーで使用する [検疫ポリシー](quarantine-policies.md) を指定する詳細な手順については、「 [PowerShell を使用してフィッシング対策ポリシーで検疫ポリシーを指定する](quarantine-policies.md#anti-phishing-policies)」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを変更する

PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合、PowerShell でフィッシング対策ルールを変更しても、追加の設定は使用できません。 この記事の「 [手順 2: PowerShell を使用してフィッシング対策ルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule) 」セクションで説明したように、ルールを作成する場合と同じ設定を使用できます。

フィッシング対策ルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを有効または無効にする

PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング詐欺対策ポリシー全体 (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効になります。 既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。

PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 」および「 [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 作成時に新しいルールの優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの _Priority_ パラメーターを使用します。

- 既定のフィッシング対策ポリシーには対応するフィッシング対策ルールがなく、変更不可の優先度値 **[最低**] が常に設定されています。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを削除する

PowerShell を使用してフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは削除されません。

PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを削除する

PowerShell を使用してフィッシング対策ルールを削除すると、対応するフィッシング対策ポリシーは削除されません。

PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを削除します。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

Defender for Office 365でフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの [**フィッシング対策**] ページで<https://security.microsoft.com/antiphishing>、ポリシーの一覧、**状態** の値、および **優先度** の値を確認します。 詳細を表示するには、一覧からポリシーを選択し、名前をクリックして表示されるポップアップで詳細を表示します。

- Exchange Online PowerShell で、ポリシーまたはルールの名前に置き換え\<Name\>、次のコマンドを実行して設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
