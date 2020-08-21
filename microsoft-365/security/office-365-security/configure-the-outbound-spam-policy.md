---
title: 送信スパム フィルターの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で送信スパム ポリシーを表示、作成、変更、削除する方法を学習できます。
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845980"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP で送信スパム フィルターを構成する

Exchange Online にメールボックスを含む Microsoft 365 組織、または Exchange Online のメールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、EOP 経由で送信される送信電子メール メッセージに対してスパム メッセージと異法な送信処理が自動的にチェックされます。

組織内のユーザーからの送信スパムは、通常、アカウントの侵害を示しています。 不審な送信メッセージは (Spam Confidence Level や SCL に関係なく) スパムとしてマークされ、サービスの評価[high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md)を保護するためにリスクの高い配信プールを経由してルーティングされます (つまり、Microsoft 365 ソースの電子メール サーバーを IP 禁止リストに含める)。 管理者は、送信電子メール アクティビティについて自動的に通知され、ユーザーは警告ポリシーによって [ブロックされます](../../compliance/alert-policies.md)。

EOP では、スパムに対する組織の全体的な防が層として送信スパム ポリシーを使用する。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定の送信スパム ポリシーを表示、編集、構成できます (削除はできません)。 さらにきめ細かく計画する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの送信スパム ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

送信スパム ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell、Exchange Online メールボックスを持つ組織のスタンドアロン EOP PowerShell) で構成できます。

EOP の送信スパム ポリシーの基本的な要素は次のとおりです。

- **送信スパム フィルター ポリシー**: 送信スパム対策フィルターの確認と通知オプションのアクションを指定します。
- **送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。

これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターで送信スパム ポリシーを管理する際には&にくいです。

- ポリシーを作成した後、実際には送信スパム フィルター ルールと、関連付けられた送信スパム フィルター ポリシーを両方に同じ名前を使用して同時に作成しています。
- ポリシーを変更すると、名前、優先順位、有効/無効の設定、および受信者フィルターに関連する設定は、送信スパム フィルター ルールを変更します。 他のすべての設定では、関連付けられた送信スパム フィルター ポリシーを変更します。
- ポリシーを削除すると、送信スパム フィルター ルールおよび関連付けられた送信スパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、このトピックで後 [述する「Exchange Online PowerShell またはスタンドアロン EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) を使用して送信スパム ポリシー」セクションを参照してください。

各組織には Default という名前の組み込みの送信スパム ポリシーがあり、以下のプロパティがあります。

- ポリシーに関連付けられた送信スパム フィルター ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

送信スパム フィルターの効果を高い方法で使用するには、特定のユーザーまたはユーザー グループに適用される、高い設定を持つ送信スパム ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 送信スパム ポリシーを追加、変更、削除するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 送信スパム ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- 送信スパム ポリシーに推奨される設定については [、「EOP 送信スパム フィルター ポリシーの設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- 電子メール送信[の制限](../../compliance/alert-policies.md)**を超え、****不**審な電子メール送信パターンが検出され、**ユーザーが**、通常の送信メール アクティビティと送信スパムによってブロックされているユーザーに関しては既にメール通知を**TenantAdmins** (**グローバル**管理者) グループのメンバーに送信できませんでした。 詳細については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>セキュリティ コンプライアンス センターを&、送信スパム ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムの送信スパム ポリシーを作成する場合、スパム フィルター ルールと、関連付けられているスパム フィルター ポリシーを両方とも同じ名前で同時に作成します。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定] ページで** 、[ **送信ポリシーの作成] をクリックします**。

3. 送信スパム **フィルター ポリシー ポップアップが** 開いたら、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

4. (省略可能)[通知 **] セクション** を展開して、不審な送信電子メール メッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。

   - **不審な送信電子メール メッセージのコピーを特定のユーザーに送信します**。 この設定により、指定されたユーザーを BCC 受信者として不審な送信メッセージに追加します。

     > [!NOTE]
     > この設定は既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。

     この設定を有効にするには:

     1. 設定を有効にするには、チェック ボックスをオンにします。

     1. [ユーザー **の追加] をクリックします**。 表示される **受信者を追加または** 削除するポップアップで、次の手順に示します。

     1. 送信者の電子メール アドレスを入力します。 複数のメール アドレスをセミコロン (.) で区切って指定;)または 1 行に 1 受信者を追加します。

     1. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックします。

        必要な回数だけこれらの手順を繰り返します。

        追加した受信者は、ポップアップ **の受信者** リスト セクションに表示されます。 受信者を削除するには、[削除] ![ ボタンをクリックします ](../../media/scc-remove-icon.png) 。

     1. 完了したら、**[保存]** をクリックします。

        この設定を無効にするには、このチェック ボックスをオフにします。

   - **送信スパムの送信によって送信者がブロックされている場合は、特定のユーザーに通知します**。

     > [!IMPORTANT]
     >
     > - この設定は、送信スパム ポリシーからの廃止処理中です。
     >
     > - 「受信者 [の制限」セクション](../../compliance/alert-policies.md) の制限を超過したために **ユーザーがブロック** されている場合、ユーザーが **ブロックされているときには、"User** Limits/**受信者の**制限" グループのメンバーに対しては既にメール通知 **を送信していない** という名前の既定のアラート ポリシー。 **管理者や他のユーザーに通知するには、送信スパム ポリシーでこの設定を使用するのではなく、アラート ポリシーを使用するように強くお勧めします**。 手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

5. (省略可能)[受信者 **の制限]** セクションを展開して、不審な送信電子メール メッセージの制限とアクションを構成します。

   > [!NOTE]
   > これらの設定は、クラウドベースのメールボックスにのみ適用されます。

   - **ユーザーあたりの最大受信者数**

     有効な値は 0 から 10000 です。 既定値は 0 で、サービスの既定値が使用されるという意味です。 詳細については、「送信の制限 [」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

     - **外部時間限値**: 1 時間あたりの外部受信者の最大数。

     - **内部時間制限 :** 1 時間あたりの内部受信者の最大数。

     - **1 日あたりの制限**: 1 日あたりの受信者の最大数。

   - **ユーザーが上記の制限を超えた**場合の処理: 受信者の制限のいずれかを超えた場合に実行 **するアクション** を構成する すべてのアクションで、ユーザーに指定されている受信者**User restricted from sending email**がメールアラート ポリシーを送信できなくなります (さらに、送信スパム ポリシー**Notify specific people if a sender is blocked due to sending outbound spam**の送信スパム設定を送信したために送信者がブロックされている場合は、特定のユーザーに通知を受信します)。

     - **ユーザーが次の日にメールを送信するのを制限**します。これは既定値です。 電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日付までメッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。

       - メール送信を制限 **された [ユーザー] というアクティビティ アラート** は、(メールおよびアラートの表示ページで) 管理者 **に通知** します。

       - ポリシーの送信スパム設定 **の送信によって送信者がブロックされている場合** 、指定した受信者もすべて通知されます。

       - ユーザーは、UTC 時間に基づいて、次の日付までメッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。

     - **ユーザーがメールを送信するのを制限**する: 電子メール通知が送信されます。ユーザーはセキュリティ & コンプライアンス センターの **[制限 <https://sip.protection.office.com/restrictedusers> **付きユーザー] ポータルに追加され、管理者が制限されたユーザー ポータルからユーザーが削除されるまで **、ユーザーはメール**を送信できません。管理者が一覧からユーザーを削除した後、その日に対して再び制限されるわけになります。 詳細については、「スパム メール [を送信した後で制限付きユーザー」 ポータルからユーザーを削除する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。

     - **操作なし、アラートのみ**: 電子メール通知が送信されます。

6. (省略可能)[ **自動転送] セクションを** 展開し、外部送信者へのユーザーによる自動転送を制御します。 自動転送の詳細については、「メール転送を [構成する」を参照してください](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)。

   > [!NOTE]
   >
   > - 2020 年 9 月前には、これらの設定は使用できますが、強制されません。
   >
   > - これらの設定は、クラウドベースのメールボックスにのみ適用されます。
   >
   > - 内部受信者への自動転送は、これらの設定の影響を受けません。

   使用できる値は次のとおりです:

   - **自動 - システム管理: 外部電子**メールの自動転送を制御するために送信スパム フィルタリングを許可します。 これは既定の値です。

   - **On:** 外部メール転送がポリシーによって無効化されていない。

   - **Off:** 外部メールの自動転送はすべてポリシーによって無効になります。

7. (必須)[ **適用対象] セクション** を展開して、ポリシーが適用される内部送信者を特定します。

    各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<sender1\>_ または _\<sender2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<sender1\>_ かつ _\<member of group 1\>_) が適用されます。

    使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。 構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。

    - **送信者ドメインが次の**場合: 組織内で構成済みの承認済みドメインの 1 つ以上の送信者を指定します。 **[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。 複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。

    - **送信者]**: 組織内の 1 人または複数のユーザーを指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 もう一度 [ **タグの追加] ボックスを** クリックして、追加の送信者を選択します。

    - **Sender が次のメンバーの場合**: 組織内の 1 つまたは複数のグループを指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 もう一度 [ **タグの追加] ボックスを** クリックして、追加の送信者を選択します。

    - **次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。 設定と動作は、条件とまったく同じです。

8. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>セキュリティ/コンプライアンス センターを&使用して送信スパム ポリシーを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定] ページで、[** 展開] ![ アイコン ](../../media/scc-expand-icon.png) をクリックして送信スパム ポリシーを展開します。

   - 送信スパム フィルター ポリシーという **名前の既定ポリシー**。

   - [種類] 列の値が「カスタムの **送信スパム** ポリシー」 **である場所に作成したカスタム ポリシー**。

3. 展開されたポリシー詳細にポリシー設定が表示されるか、ポリシーの編集を **クリックすることができます**。

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>セキュリティ コンプライアンス センターを&変更して送信スパム ポリシーを変更する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定] ページで、[** 展開] ![ アイコン ](../../media/scc-expand-icon.png) をクリックして送信スパム ポリシーを展開します。

   - 送信スパム フィルター ポリシーという **名前の既定ポリシー**。

   - [種類] 列の値が「カスタムの **送信スパム** ポリシー」 **である場所に作成したカスタム ポリシー**。

3. **[ポリシーの編集]** をクリックします。

カスタム送信スパム ポリシーの場合、表示されるポップアップで使用できる設定は、「セキュリティ & コンプライアンス センターを使用して送信スパム ポリシーを作成 [する」セクションで説明されている設定と同じ](#use-the-security--compliance-center-to-create-outbound-spam-policies) です。

「送信スパム フィルター ポリシー」という名前 **の既定の送信スパム ポリシー**の場合、 **セクション** に適用は使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。

ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。

### <a name="enable-or-disable-outbound-spam-policies"></a>送信スパム ポリシーを有効または無効にする

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定] ページで、[** ![ 展開] アイコンをクリックして、作成したカスタム ](../../media/scc-expand-icon.png) ポリシーを展開します ([種類] **列** の値は **「カスタム送信スパム ポリシー」です**)。

3. 展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。

   ポリシーを無効にするには、左に切り替えます。 ![オフに切り替え](../../media/scc-toggle-off.png)

   ポリシーを有効にするには、右に切り替えます。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

既定の送信スパム ポリシーを無効にすることはできません。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーの優先度を設定する

既定では、送信スパム ポリシーには、ポリシーの作成順序に基づく優先度が設定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

カスタムの送信スパム ポリシーは、処理される順に表示されます (最初のポリシーの **Priority** 値が 0)。 「Outbound スパム フィルター ポリシー」 **という名前の既定の送信スパム** ポリシーの優先度 **は「最低**」で、変更できません。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム**対策の設定] ページで**、[種類] 列の値が**カスタムの送信スパム****ポリシーであるポリシーを見つける。** **[優先度]** 列の値に注目します。

   - 優先度が最も高いカスタム送信スパム ポリシーの値は、下矢 ![ 印アイコン ](../../media/ITPro-EAC-DownArrowIcon.png) **0 です**。

   - 最も低い優先度を持つカスタム送信スパム ポリシーの値 ![ は上矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (たとえば、 ![ 上矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png) **3) です**。

   - 3 つ以上のカスタム送信スパム ポリシーがある場合、最も優先度の高い優先度と最も小さい間のポリシーでは、上矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ n ](../../media/ITPro-EAC-DownArrowIcon.png) の値が**表示されます**(たとえば、上矢印アイコン ![ の下矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)。**

3. 上 ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) または ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) 優先度リストのカスタム送信スパム ポリシーを上下に移動します。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>セキュリティ コンプライアンス センター&、送信スパム ポリシーの削除

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定] ページで、[** ![ 展開] アイコンを ](../../media/scc-expand-icon.png) クリックして、削除するカスタム ポリシーを展開します **([種類** ] 列は **「カスタム送信スパム ポリシー」です**)。

3. 展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。

4. 警告ダイアログが表示されたら、**[はい]** をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する

前述のとおり、送信スパム ポリシーは送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いは明らかです。 ** \* -HostedOutboundSpamFilterPolicy**コマンドレットを使用して送信スパム フィルター ポリシーを管理し、送信スパム フィルター ルールを管理するには** \* 、-HostedOutboundSpamFilterRule コマンドレットを**使用します。

- PowerShell では、最初に送信スパム フィルター ポリシーを作成し、次にルールが適用されるポリシーを特定する送信スパム フィルター ルールを作成します。
- PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの設定は別々に変更されます。
- PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動で削除されず、逆もまた同じくなります。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell を使用して送信スパム ポリシーを作成する

PowerShell で送信スパム ポリシーを作成する手順は 2 つの手順で行います。

1. 送信スパム フィルター ポリシーを作成します。
2. ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。

 **注**:

- 新しい送信スパム フィルター ルールを作成して、既存の関連付けされていない送信スパム フィルター ポリシーをそのトランスポート ルールに割り当てたりすることができます。 送信スパム フィルター ルールを複数の送信スパム フィルター ポリシーに関連付けられるルールは使用できません。

- ポリシーを作成しない限りセキュリティ/コンプライアンス センターでは使用できない次 &の設定を、PowerShell の新しい送信スパム フィルター ポリシーに構成できます。

  - 無効化された新しいポリシーを作成_します_ `$false` **(New-HostedOutboundSpamFilterRule コマンドレットで有効** )。
  - 作成中にポリシーの優先度を設定する (_優先_ _\<Number\>_ 順位) **は、New-HostedOutboundSpamFilterRule コマンドレットで設定** します。

- ポリシーをスパム フィルター ルールに割り当てるまで、PowerShell で作成した新しい送信スパム フィルター ポリシーは、セキュリティ & コンプライアンス センターに表示されません。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する

送信スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次のような設定で Contoso Executives という新しい送信スパム フィルター ポリシーを作成します。

- 受信者レートの制限は、既定値の小さい値に制限されています。 詳細については [、「Microsoft 365 オプション間の送信制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 制限の 1 つに達すると、ユーザーはメッセージを送信できません。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する

送信スパム フィルター ルールを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次に示す設定で Contoso Executives という新しい送信スパム フィルター ルールを作成します。

- Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられていいます。

- ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを表示する

すべての送信スパム フィルター ポリシーの要約リストを返すには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

特定の送信スパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

この例では、Executives という送信スパム フィルター ポリシーのすべてのプロパティの値が返されます。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを表示する

既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

すべての送信スパム フィルター ルールの要約リストを返すには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterRule
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

特定の送信スパム フィルター ルールに関する詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティの値が返されます。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを変更する

PowerShell でマルウェア フィルター ポリシーを変更する場合と、このトピックで前述した [手順 1 で説明](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) したように、ポリシーを作成する場合と同じ設定を使用できます。

> [!NOTE]
> 送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy コマンドレット** には _Name_ パラメーターはありません)。 セキュリティ コンプライアンス センターで送信スパム ポリシーの名前を変更する&、送信スパム フィルター ルールの名前のみを変更 _します_。

送信スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを変更する

PowerShell で送信スパム フィルター ルールを変更するときに使用できない設定は _、無効なルール_ の作成を可能にする Enabled パラメーターだけです。 既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合、PowerShell で送信スパム フィルター ルールを変更する際に利用可能な追加の設定は存在しない。 手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する手順の前述のセクションに示したとおりです。

送信スパム フィルター ルールを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを有効または無効にする

PowerShell で送信スパム フィルター ルールを有効化または無効化すると、送信スパム ポリシー全体 (送信スパム フィルター ルールおよび割り当てられた送信スパム フィルター ポリシー) が有効または無効になります。 既定の送信スパム ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。

PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ルールを無効化します。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [Disable-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で送信スパム フィルター ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 新しく作成したルールの優先度を設定するには、**代わりに、New-HostedOutboundSpamFilterRule コマンドレットの** _Priority_パラメーターを使用します。
>
> - 送信された既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールがありません。常に、変更不可能な優先度の値 **Lowest が設定されています**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを削除する

PowerShell を使用して送信スパム フィルター ポリシーを削除した場合、対応する送信スパム フィルター ルールは削除されません。

PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という送信スパム フィルター ポリシーを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを削除する

PowerShell を使用して送信スパム フィルター ルールを削除した場合は、対応する送信スパム フィルター ポリシーは削除されません。

PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>詳細情報

[制限されたユーザー ポータルからブロックされたユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)

[自動転送済みメッセージレポート](mfi-auto-forwarded-messages-report.md)
