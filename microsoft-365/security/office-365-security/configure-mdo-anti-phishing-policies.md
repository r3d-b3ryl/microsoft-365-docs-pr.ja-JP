---
title: Microsoft Defender でフィッシング対策ポリシーを構成Office 365
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
description: 管理者は、Microsoft Defender を使用している組織で利用可能な高度なフィッシング対策ポリシーを作成、変更、および削除する方法をOffice 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 28dcfb3c914dd14ad9184f73c25c3469d2fa85d4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210487"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender でフィッシング対策ポリシーを構成Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃や他の種類のフィッシング攻撃から組織を保護するのに役立ちます。 Exchange Online Protection (EOP) のフィッシング対策ポリシーと microsoft Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については、「フィッシング対策保護」を参照[してください](anti-phishing-protection.md)。

管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。 さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

Defender のフィッシング対策ポリシーは、Office 365ポータルまたは PowerShell Microsoft 365 Defender構成Exchange Onlineできます。

Exchange Online Protection で使用できるフィッシング対策ポリシー (つまり、Office 365 の Defender を使用しない組織) の構成の詳細については[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」を参照してください。

フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、フィッシング対策ポリシーを管理する際に、Microsoft 365 Defenderされません。

- ポリシーを作成すると、実際には両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。 その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。
- ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。

PowerShell Exchange Onlineでは、ポリシーとルールを個別に管理します。 詳細については、この記事の[後半Exchange Online「PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)を使用してフィッシング対策ポリシーを構成する」を参照してください。

すべての Defender for Office 365には、次のプロパティを持つ antiPhish Default という名前Office 365フィッシング対策ポリシーが組み込みされています。

- ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

Office 365 の Defender でのフィッシング対策保護の有効性を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定でカスタムフィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 フィッシング対策ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります <sup>\*</sup> 。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- Defender for Office 365 でのフィッシング対策ポリシーの推奨設定については、「Defender for Office 365 設定」[を参照してください](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderを作成するには、このポータルを使用します。

Microsoft 365 Defender ポータルでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページで、[作成** ] アイコン ![ をクリックします。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. ポリシー ウィザードが開きます。 [ポリシー名 **] ページで** 、次の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。 ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[フィッシング&のしきい値** ] ページで、次の設定を構成します。

   - **フィッシングメールのしきい値**: スライダーを使用して、次のいずれかの値を選択します。
     - **1 - Standard** (既定値です)。
     - **2 - アグレッシブ**
     - **3 - より積極的**
     - **4 - 最も積極的**

     詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの高度[なフィッシングのしきい値」を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。

   - **偽装**: これらの設定は、受信メッセージの差出人アドレスで特定の送信者が (個別に、またはドメインごとに) 検索するポリシーの条件です。 詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの偽装[設定」を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。

     > [!NOTE]
     >
     > - 各フィッシング対策ポリシーでは、最大 350 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。 複数のポリシーで同じ保護されたユーザーを指定できない。
     > - 送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。 送信者と受信者がメールで通信したことがない場合、メッセージは偽装の試みとして識別されます。

     - **ユーザーの保護を有効** にする : 既定値はオフ (選択されていない) です。 オンにする場合は、チェック ボックスをオンにし、表示される **[送信者の管理] (nn)** リンクをクリックします。

       表示される **偽装保護の送信者の** 管理フライアウトで、次の手順を実行します。

       - **内部送信者:**[内部アイコン ![ の追加] をクリックします。](../../media/m365-cc-sc-add-internal-icon.png) **[内部] を選択します**。 表示される **[内部送信者の追加]** フライアウトで、ボックス内をクリックし、一覧から内部ユーザーを選択します。 リストをフィルター処理するには、ユーザーを入力し、結果からユーザーを選択します。 ほとんどの識別子 (名前、表示名、エイリアス、メール アドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。

         必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

         完了したら、[追加] を **クリックします。**

       - **外部送信者:**[外部アイコン ![ の追加] をクリックします。](../../media/m365-cc-sc-create-icon.png) **[外部] を選択します**。 表示される **[外部送信者** の追加] フライアウトで、[名前の追加]ボックスに表示名を入力し、[空きメールの追加] ボックスに電子メール アドレスを入力し、[追加] をクリック **します**。

         必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

         完了したら、[追加] を **クリックします。**

       [偽装の **送信者の** 管理] フライアウトに戻り、リストから 1 つ以上のエントリを選択してエントリを削除できます。 [検索] アイコンを使用してエントリ ![ を検索できます。](../../media/m365-cc-sc-create-icon.png) **[検索** ] ボックス。

       少なくとも 1 つのエントリを選択すると、[選択 ![ したユーザーの削除] アイコンが表示されます。](../../media/m365-cc-sc-remove-selected-users-icon.png) **[選択したユーザーの削除** ] アイコンが表示され、選択したエントリを削除できます。

       完了したら、[**完了**] をクリックします。

     - **保護するドメインを有効** にする: 既定値はオフ (選択されていない) です。 オンにするには、チェック ボックスをオンにし、表示される次の設定の一方または両方を構成します。
       - **所有するドメインを含める**: この設定を有効にする場合は、チェック ボックスをオンにします。 所有しているドメインを表示するには、[自分のドメインの **表示] をクリックします**。
       - **カスタム ドメインを含** める : この設定を有効にする場合は、チェック ボックスをオンにして、表示される **[管理] (nn)** カスタム ドメインのリンクをクリックします。 表示される **偽装保護用の** カスタム ドメインの管理フライアウトで、[ドメインの追加 ![ ] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **ドメインを追加する**。

         表示される **[カスタム ドメイン** の追加] フライアウトで、[ドメイン] ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

         完了したら、[ドメインの追加] **をクリックします。**

         > [!NOTE]
         > すべてのフィッシング対策ポリシーに最大 50 のドメインを設定できます。

       偽装用の **カスタム ドメイン** の管理フライアウトに戻り、リストから 1 つ以上のエントリを選択してエントリを削除できます。 [検索] アイコンを使用してエントリ ![ を検索できます。](../../media/m365-cc-sc-create-icon.png) **[検索** ] ボックス。

       少なくとも 1 つのエントリを選択すると、[ ![ ドメインの削除] アイコンが表示されます。](../../media/m365-cc-sc-delete-icon.png) **[** 削除] アイコンが表示され、選択したエントリを削除するために使用できます。

   - **信頼できる送信者と** ドメインを追加する : : [管理] **(nn)** 信頼できる送信者とドメインをクリックして、ポリシーの偽装保護の例外を指定します。 表示される **偽装保護用** のカスタム ドメインの管理フライアウトで、次の設定を構成します。
      - **[送信者**] : [送信者] **タブが** 選択され、[送信者の追加] アイコン ![ をクリックします ](../../media/m365-cc-sc-create-icon.png) 。 [信頼 **できる送信者の追加]** フライアウトが表示されたら、ボックスに電子メール アドレスを入力し、[追加] を **クリックします**。 必要な回数だけこの手順を繰り返します。 既存のエントリを削除するには、エントリの ![ [削除] ](../../media/m365-cc-sc-close-icon.png) アイコンをクリックします。

        完了したら、**[追加]** をクリックします。

      - **ドメイン:**[ドメイン] タブ **を選択** し、[ドメインの ![ 追加] アイコンをクリックします ](../../media/m365-cc-sc-create-icon.png) 。

        [信頼 **できるドメイン** の追加] フライアウトが表示されたら、[ドメイン] ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

        完了したら、**[追加]** をクリックします。

     偽装用の **カスタム** ドメインの管理フライアウトに戻り、リストから 1つ以上のエントリを選択して、[送信者] タブと [ドメイン] タブからエントリを削除できます。 [検索] アイコンを使用してエントリ ![ を検索できます。](../../media/m365-cc-sc-create-icon.png) **[検索** ] ボックス。

     少なくとも 1 つのエントリを選択すると、[ **削除** ] アイコンが表示され、選択したエントリを削除できます。

     完了したら、[**完了**] をクリックします。

   - **メールボックス インテリジェンスを有効** にする: 既定値はオン (選択) であり、オンのままにすることをお勧めします。 オフにする場合は、チェック ボックスをオフにします。

     - **インテリジェンス ベースの偽装保護を有効** にする: この設定は、[メールボックス インテリジェンスを有効にする **]** がオン (選択) の場合にのみ使用できます。 この設定では、偽装の試行として識別されるメッセージに対してメールボックス インテリジェンスがアクションを実行できます。 次のページの [メールボックスインテリジェンスが偽装ユーザーを検出する場合] の設定で実行するアクションを指定します。

       この設定は、チェック ボックスをオンにすることをお勧めします。 この設定をオフにするには、チェック ボックスをオフにします。

   - **ス** プーフィング : このセクションでは、[ス **プーフィング** インテリジェンスを有効にする] チェック ボックスを使用して、スプーフィング インテリジェンスのオンとオフを切り替えます。 既定値はオン (選択) であり、オンのままにすることをお勧めします。 次のページの [メッセージがスプーフィングとして検出された場合]の設定で、ブロックされたスプーフィングされた送信者からのメッセージに対して実行するアクションを指定します。

     スプーフィング インテリジェンスをオフにするには、チェック ボックスをオフにします。

     > [!NOTE]
     > MX レコードがスプーフィング対策保護をオフにする必要Microsoft 365。代わりに、コネクタの拡張フィルターを有効にできます。 手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   完了したら、**[次へ]** をクリックします。

6. **[アクション]** ページが表示されたら、次の設定を構成します。

   - **メッセージアクション**: このセクションで次のアクションを構成します。
     - **偽装ユーザーとしてメッセージが** 検出された場合: この設定は、[前のページでユーザーを保護する] を選択した場合にのみ使用できます。 送信者が前のページで指定した保護されたユーザーの 1 人であるメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他の電子メール アドレスにリダイレクトする**
       - **受信者の迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫** する: このアクションを選択すると、[検疫ポリシーの適用] ボックスが表示され、ユーザー偽装保護によって検疫されたメッセージに適用される検疫ポリシーを選択します。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         [検疫 **ポリシーの適用]** の値が空白の場合は、既定の検疫ポリシーが使用されます (ユーザー偽装検出の場合は DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。
  
       - **メッセージを配信し、他のアドレスを Bcc 行に追加する**
       - **配信前にメッセージを削除する**

     - **メッセージが偽装ドメインとして** 検出された場合: この設定は、前のページで [保護するドメインを有効にする] を選択した場合にのみ使用できます。 送信者の電子メール アドレスが前のページで指定した保護されたドメインの 1 つにあるメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他の電子メール アドレスにリダイレクトする**
       - **受信者の迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫** する: このアクションを選択すると、[検疫ポリシーの適用] ボックスが表示され、ドメイン偽装保護によって検疫されたメッセージに適用される検疫ポリシーを選択します。

         [検疫 **ポリシーの適用]** の値が空白の場合は、既定の検疫ポリシーが使用されます (ドメイン偽装検出の場合は DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

       - **メッセージを配信し、他のアドレスを Bcc 行に追加する**
       - **配信前にメッセージを削除する**

     - **メールボックス インテリジェンスが偽装** ユーザーを検出した場合: この設定は、前のページで [偽装保護のインテリジェンスを有効にする] を選択した場合にのみ使用できます。 メールボックス インテリジェンスによって偽装の試行として識別されたメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。
       - **アクションを適用しない**
       - **メッセージを他の電子メール アドレスにリダイレクトする**
       - **受信者の迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[検疫ポリシーの適用] ボックスが表示され、メールボックス インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         [検疫 **ポリシーの適用]** の値が空白の場合は、既定の検疫ポリシーが使用されます (メールボックス インテリジェンス検出の場合は DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

       - **メッセージを配信し、他のアドレスを Bcc 行に追加する**
       - **配信前にメッセージを削除する**

     - **メッセージがスプーフィングとして検出された** 場合: この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。 ブロックされたスプーフィングされた送信者からのメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。
       - **受信者の迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫する**: このアクションを選択すると、[検疫ポリシーの適用] ボックスが表示され、スプーフィング インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

         [検疫 **ポリシーの適用]** の値が空白の場合は、既定の検疫ポリシーが使用されます (スプーフィング インテリジェンス検出の場合は DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

   - **安全に関&:** 次の設定を構成します。
     - **最初の連絡先の安全性のヒント** を表示する : 詳細については [、「First contact 安全性のヒント」 を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。
     - **[ユーザーの偽装** 安全性のヒントを表示する: この設定は、[前のページでユーザーを保護する] を選択 **した** 場合にのみ使用できます。
     - **[ドメイン偽装の** 安全性のヒントを表示する] : この設定は、[前のページで保護するドメインを有効にする] を選択した場合にのみ使用できます。
     - **ユーザー偽装の異常な文字を表示安全性のヒント** この設定は、[ユーザーの保護を有効にする] または [前のページで保護するドメインを有効にする] を選択 **した** 場合にのみ使用できます。
     - **スプーフィング** の認証されていない送信者に対して表示 (?) : この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。 メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合は、Outlook の [差出人] ボックスの送信者の写真に疑問符を[追加](email-validation-and-authentication.md#composite-authentication)します。
     - **"via" タグを表示** する : この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。 DKIM 署名または chris@contoso.com MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で) を **追加** します。 既定値はオン (選択) です。 オフにする場合は、チェック ボックスをオフにします。

     設定を有効にする場合は、チェック ボックスをオンにします。 オフにする場合は、チェック ボックスをオフにします。

   完了したら、**[次へ]** をクリックします。

7. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

8. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderを表示するには、このポータルを使用します。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページ** では、フィッシング対策ポリシーの一覧に次のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **最終更新日時**

3. 名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderポータルを使用して変更する

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「[](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)フィッシング対策ポリシーを作成Microsoft 365 Defenderを使用してフィッシング対策ポリシーを作成する」を参照してください。

   既定のフィッシング対策ポリシーでは、[ユーザー、グループ、ドメイン] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーを有効または無効にする

既定のフィッシング対策ポリシーを無効にできない。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーの優先度を設定する

既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。 ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- このポータルMicrosoft 365 Defender、フィッシング対策ポリシーの優先度を変更できるのは、作成後のみです。 PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。
- フィッシング対策ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。 既定のフィッシング対策ポリシーの優先度の値は **[最低**] で、変更は行えなくないます。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - 優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。
   - 優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。
   - 3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>カスタムフィッシングMicrosoft 365 Defenderポリシーを削除するには、このポータルを使用します。

Microsoft 365 Defenderポータルを使用してカスタムフィッシング対策ポリシーを削除すると、フィッシング対策ルールと対応するフィッシング対策ポリシーの両方が削除されます。 既定のフィッシング対策ポリシーを削除できない。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&[&脅威ポリシーのフィッシング対策] に \>  \>  \> **移動** します。

2. [フィッシング **対策] ページ** で、ポリシーの名前をクリックして、リストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>PowerShell Exchange Onlineを使用してフィッシング対策ポリシーを構成する

前述したように、スパム対策ポリシーはフィッシング対策ポリシーとフィッシング対策ルールで構成されています。

PowerShell Exchange Online、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。 -AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***

- PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。

1. フィッシング対策ポリシーを作成します。
2. ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注意**:

- 新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。 フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。
- ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない PowerShell の新しいフィッシング対策ポリシーで次の設定を構成できます。
  - 無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。
- PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- ポリシーが有効になっています (Enabled パラメーターは使用していないので、既定値はです `$true` )。
- 説明は、調査部門のポリシーです。
- スプーフィング検出の既定のアクションを [検疫] に [](quarantine-policies.md)変更し、検疫済みメッセージに既定の検疫ポリシーを使用します (スプーフィングクォンティンタグ パラメーターは _使用_ しません)。
- すべての受け入れドメインに対する組織のドメイン保護と、ドメインの保護を対象 fabrikam.com。
- ドメイン偽装検出のアクションとして検疫を指定し、検疫されたメッセージに既定の [](quarantine-policies.md)検疫ポリシーを使用します _(TargetedDomainQuarantineTag_ パラメーターは使用しません)。
- 偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。
- ユーザー偽装検出のアクションとして検疫を指定し、検疫されたメッセージに既定の [](quarantine-policies.md)検疫ポリシーを使用します _(TargetedUserQuarantineTag_ パラメーターは使用しません)。
- メールボックス インテリジェンス _(EnableMailboxIntelligence)_ を有効にし、メールボックス インテリジェンス保護がメッセージに対してアクションを実行できます _(EnableMailboxIntelligenceProtection)_ は、[](quarantine-policies.md)検出されたメッセージのアクションとして検疫を指定し、検疫されたメッセージの既定の検疫ポリシーを使用します _(MailboxIntelligenceQuarantineTag_ パラメーターは使用しません)。
- すべての安全に関するヒントを有効にする。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。

> [!NOTE]
> フィッシング対策ポリシーで使用する検疫ポリシー[](quarantine-policies.md)を指定する詳細な手順については[、「Use PowerShell](quarantine-policies.md#anti-phishing-policies)を使用してフィッシング対策ポリシーで検疫ポリシーを指定する」を参照してください。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシング対策ルールを作成する

フィッシング対策ルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件を使用して、Research Department という名前のフィッシング対策ルールを作成します。

- ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文とパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを表示する

既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要リストを返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文とパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを表示する

既存のフィッシング対策ルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共に、すべてのフィッシング対策ルールの概要リストを返します。

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

構文とパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを変更する

次の項目以外にも、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」セクションで説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。

- 指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に優先度が最も低く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。

- フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。 Microsoft 365 Defender ポータルでフィッシング対策ポリシーの名前を変更すると、フィッシング対策ルールの名前が変更 _されます_。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。

> [!NOTE]
> フィッシング対策ポリシーで使用する検疫ポリシー[](quarantine-policies.md)を指定する詳細な手順については[、「Use PowerShell](quarantine-policies.md#anti-phishing-policies)を使用してフィッシング対策ポリシーで検疫ポリシーを指定する」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを変更する

PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、PowerShell でフィッシング対策ルールを変更するときに追加の設定を使用できません。 この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成するときにも同じ設定を使用できます。

フィッシング対策ルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを有効または無効にする

PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効となります。 既定のフィッシング対策ポリシーを有効または無効にできない (すべての受信者に常に適用されます)。

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

構文とパラメーターの詳細については [、「Enable-AntiPhishRule」](/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](/powershell/module/exchange/disable-antiphishrule)。

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

- 新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの Priority パラメーターを使用します。 

- 既定のフィッシング対策ポリシーには、対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値が **[最低**] です。

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

構文とパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Remove-AntiPhishPolicy)。

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

構文とパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次Office 365手順を実行します。

- [ポリシー] Microsoft 365 Defenderで、[ポリシー] セクション& [ &フィッシング対策ポリシー] に移動 \>  \>  \> します。  ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、名前をクリックして表示されるフライアウトの詳細を表示して、一覧からポリシーを選択します。

- PowerShell Exchange Online、ポリシーまたはルールの名前に置き換え、次のコマンドを \<Name\> 実行して設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
