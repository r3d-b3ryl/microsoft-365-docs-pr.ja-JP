---
title: 送信スパム フィルターを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で送信スパム ポリシーを表示、作成、変更、および削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 742c58a8a94938c5896382a6d53acac127974f02
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288935"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP で送信スパム フィルターを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP 経由で送信される送信電子メール メッセージがスパムや異常な送信アクティビティについて自動的にチェックされます。

組織内のユーザーからの送信スパムは、通常、侵害されたアカウントを示します。 不審な送信メッセージは(スパム信頼度または SCL に関係なく) スパムとしてマークされ、サービスの[](high-risk-delivery-pool-for-outbound-messages.md)評判を保護するために危険度の高い配信プールを経由してルーティングされます (つまり、Microsoft 365 ソースメール サーバーを IP ブロック リストから保護します)。 管理者は、警告ポリシーを使用して、疑わしい送信メール アクティビティとブロックされたユーザーに自動的 [に通知されます](../../compliance/alert-policies.md)。

EOP は、スパムに対する組織の全体的な防御の一環として送信スパム ポリシーを使用します。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定の送信スパム ポリシーを表示、編集、および構成 (削除しない) できます。 よりきめ細かく管理するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタム送信スパム ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

送信スパム ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で構成できます。

EOP の送信スパム ポリシーの基本的な要素は次のとおりです。

- **送信スパム フィルター ポリシー**: 送信スパム フィルターの条件と通知オプションのアクションを指定します。
- **送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、セキュリティ/コンプライアンス センターで送信スパム ポリシーを管理&明らかではありません。

- ポリシーを作成する場合、実際には、両方に同じ名前を使用して、送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によって送信スパム フィルター ルールが変更されます。 その他のすべての設定は、関連付けられた送信スパム フィルター ポリシーを変更します。
- ポリシーを削除すると、送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、後の [「Exchange Online PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する」を参照してください。

すべての組織には、次のプロパティを持つ Default という名前の組み込みの送信スパム ポリシーがあります。

- ポリシーに関連付けられている送信スパム フィルター ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

送信スパム フィルターの効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定を使用して、カスタムの送信スパム ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - 送信スパム ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - 送信スパム ポリシーへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要があります**。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 送信スパム ポリシーの推奨設定については、「EOP 送信スパム フィルター ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- [電子メール送信の制限] という名前の既定のアラート ポリシーが超過しました。不審な電子メール送信パターンが検出されました。また、ユーザーが既に **TenantAdmins** **(グローバル** 管理者) グループのメンバーに電子メール通知を送信し、送信スパムによる異常な送信電子メール アクティビティとブロックされたユーザーに関する電子メール通知を送信できません。 [](../../compliance/alert-policies.md) 詳細については、「制限されたユーザー [のアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>セキュリティ/コンプライアンス センター&使用して送信スパム ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムの送信スパム ポリシーを作成すると、両方に同じ名前を使用して、スパム フィルター ルールと関連付けられたスパム フィルター ポリシーが同時に作成されます。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで** 、[送信ポリシーの **作成] をクリックします**。

3. 開く **送信スパム フィルター ポリシー** のフライアウトで、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

4. (省略可能)[通知] **セクションを** 展開して、不審な送信電子メール メッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。

   - **不審な送信電子メール** メッセージのコピーを特定のユーザーに送信する: この設定では、指定したユーザーを BCC 受信者として不審な送信メッセージに追加します。

     > [!NOTE]
     > この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。

     この設定を有効にするには:

     1. この設定を有効にするには、チェック ボックスをオンにします。

     1. [ユーザー **の追加] をクリックします**。 表示される **受信者の追加または削除** のフライアウトで、次のようにします。

     1. 送信者の電子メール アドレスを入力します。 複数の電子メール アドレスをセミコロンで区切って指定;)または 1 行に 1 人の受信者。

     1. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックして受信者を追加します。

        必要な回数だけこれらの手順を繰り返します。

        追加した受信者は、フライアウトの **[受信者一覧** ] セクションに表示されます。 受信者を削除するには、[削除] ボタン ![ をクリックします ](../../media/scc-remove-icon.png) 。

     1. 完了したら、**[保存]** をクリックします。

        この設定を無効にするには、チェック ボックスをオフにします。

   - **送信スパムの送信によって送信者がブロックされた場合は、特定のユーザーに通知します**。

     > [!IMPORTANT]
     >
     > - この設定は、送信スパム ポリシーから廃止中です。
     >
     > - ユーザーが [](../../compliance/alert-policies.md)[受信者の制限] セクションの制限を超えてブロックされている場合、User という名前の既定のアラート ポリシーは **、TenantAdmins** (**グローバル** 管理者) グループのメンバーに既に電子メール通知を送信します。 **送信スパム ポリシーでは、この** 設定ではなくアラート ポリシーを使用して、管理者や他のユーザーに通知することを強く推奨します。 手順については、「制限されたユーザー [のアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

5. (省略可能)[受信者 **の制限] セクションを展開** して、疑わしい送信電子メール メッセージの制限とアクションを構成します。

   > [!NOTE]
   > これらの設定は、クラウドベースのメールボックスにのみ適用されます。

   - **ユーザーあたりの最大受信者数**

     有効な値は 0 ~ 10000 です。 既定値は 0 で、サービスの既定値が使用されます。 詳細については、「送信の [制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

     - **外部時間制限**: 1 時間あたりの外部受信者の最大数。

     - **内部時間制限**: 1 時間あたりの内部受信者の最大数。

     - **1 日** あたりの制限 : 1 日あたりの受信者の最大数。

   - **ユーザーが上記の** 制限を超えた場合のアクション : 受信者の制限のいずれかを超えた場合に実行する **アクションを構成** します。 すべてのアクションについて **、User** で指定された受信者が電子メール通知ポリシーの送信を制限しました (また、送信スパム ポリシーの送信スパム設定によって送信者がブロックされた場合、現在は冗長な **Notify** 特定のユーザーで、電子メール通知を受信します)。

     - **次の日までメールを送信** するユーザーを制限する : これは既定値です。 電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までそれ以上メッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。

       - ユーザーという名前のアクティビティ アラート **は、(** メールと [アラートの表示] ページで) 管理者に **通知します。**

       - ポリシーで送信スパム設定を送信するために送信者がブロックされた場合は、特定のユーザーに通知で指定された受信者も通知されます。

       - ユーザーは、UTC 時間に基づいて、次の日までそれ以上メッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。

     - **メール** の送信を制限する : 電子メール通知が送信され、セキュリティ & コンプライアンス センターの [制限されたユーザー **] <https://sip.protection.office.com/restrictedusers>** ポータルにユーザーが追加され、ユーザーは管理者によって制限付きユーザー ポータルから削除されるまで電子メールを送信できません。管理者が一覧からユーザーを削除した後、その日のユーザーは再び制限されません。 手順については、「迷惑メールの送信後に制限付きユーザー ポータルからユーザーを削除する」 [を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。

     - **アクションなし、アラートのみ**: 電子メール通知が送信されます。

6. (省略可能)[ **自動転送] セクションを** 展開して、ユーザーによる外部送信者への電子メールの自動転送を制御します。 詳細については [、「Microsoft 365](external-email-forwarding.md)で外部メールの自動転送を制御する」を参照してください。

   > [!NOTE]
   >
   > - 2020 年 9 月以前は、これらの設定は使用できますが、適用されません。
   >
   > - これらの設定は、クラウドベースのメールボックスにのみ適用されます。
   >
   > - 自動転送を無効にすると、外部の送信者が転送先のメールボックスにメールを送信すると、受信者は配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を受信します。 メッセージが内部送信者によって送信され、転送方法がメールボックス転送 [](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_(SMTP_ 転送とも呼ばれる) である場合、内部送信者は NDR を取得します。 受信トレイ ルールが原因で転送が発生した場合、内部送信者は NDR を受け取らない。

   使用できる値は次のとおりです:

   - **自動 - システム制御**: 送信スパム フィルターを使用して外部電子メールの自動転送を制御できます。 これが既定値です。
   - **オン**: ポリシーによって外部電子メールの自動転送が無効にされません。
   - **オフ**: ポリシーによってすべての外部電子メールの自動転送が無効になります。

7. (必須)[適用 **対象] セクションを** 展開して、ポリシーが適用される内部送信者を特定します。

    各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<sender1\>_ または _\<sender2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<sender1\>_ かつ _\<member of group 1\>_) が適用されます。

    使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。 構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。

    - **送信者ドメイン:** 組織内で構成されている 1 つ以上の承認されたドメインの送信者を指定します。 **[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。 複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。

    - **送信者:** 組織内の 1 人または複数のユーザーを指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 もう一度 [ **タグの追加] ボックスをクリック** して、追加の送信者を選択します。

    - **Sender が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 もう一度 [ **タグの追加] ボックスをクリック** して、追加の送信者を選択します。

    - **次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。 設定と動作は、条件とまったく同じです。

8. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>セキュリティ/コンプライアンス センター&使用して送信スパム ポリシーを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで、[** 展開] アイコンをクリックして ![ ](../../media/scc-expand-icon.png) 送信スパム ポリシーを展開します。

   - 送信スパム フィルター ポリシー **という名前の既定のポリシー**。

   - [種類] 列の値がカスタム送信スパムポリシーである **カスタム ポリシーを作成しました**。

3. ポリシー設定は、展開されたポリシーの詳細に表示されます。表示される場合は、[ポリシーの編集] を **クリックします**。

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>セキュリティ/コンプライアンス センター&使用して送信スパム ポリシーを変更する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで、[** 展開] アイコンをクリックして ![ ](../../media/scc-expand-icon.png) 送信スパム ポリシーを展開します。

   - 送信スパム フィルター ポリシー **という名前の既定のポリシー**。

   - [種類] 列の値がカスタム送信スパムポリシーである **カスタム ポリシーを作成しました**。

3. **[ポリシーの編集]** をクリックします。

カスタム送信スパム ポリシーの場合、表示されるフライアウトで使用可能な設定は、「セキュリティ & コンプライアンス センター[](#use-the-security--compliance-center-to-create-outbound-spam-policies)を使用して送信スパム ポリシーを作成する」セクションで説明されている設定と同じです。

送信スパム フィルター ポリシーという名前の既定の送信スパム ポリシーの場合、[適用対象] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更できません。

ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。

### <a name="enable-or-disable-outbound-spam-policies"></a>送信スパム ポリシーを有効または無効にする

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定**] ページで、[展開] アイコンをクリックして、作成したカスタム ポリシーを展開します ([種類] 列の値は ![ ](../../media/scc-expand-icon.png) **[カスタム送信** スパム ポリシー] です)。

3. 展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。

   ポリシーを無効にするには、左に切り替えます。 ![オフに切り替え](../../media/scc-toggle-off.png)

   ポリシーを有効にするには、右に切り替えます。 ![オンに切り替え](../../media/scc-toggle-on.png)

既定の送信スパム ポリシーを無効にできない。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーの優先度を設定する

既定では、送信スパム ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

カスタム送信スパム ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。 "送信スパム フィルター ポリシー  " という名前の既定の送信スパム ポリシーの優先度の値は **"最低**" であり、変更できます。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム **対策の設定]** ページで、[種類] 列の値が[カスタム送信スパム ポリシー] である **ポリシーを探します**。 **[優先度]** 列の値に注目します。

   - 優先度が最も高いカスタム送信スパム ポリシーの値は、 ![ 下方向キー アイコン ](../../media/ITPro-EAC-DownArrowIcon.png) **0 です**。

   - 優先度が最も低いカスタム送信スパム ポリシーの値は、上方向キー アイコン n (上矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png) 3 など) ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **です**。

   - 3 つ以上のカスタム送信スパム ポリシーがある場合は、最高と最低の優先度の間のポリシーの値が上方向キー アイコンの下矢印アイコン n (たとえば、上方向キー ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ アイコンの下矢印アイコン ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)** になります。

3. 上 ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) または ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) を使用して、カスタム送信スパム ポリシーを優先度リスト内で上下に移動します。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>セキュリティ/コンプライアンス センター&使用して送信スパム ポリシーを削除する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定**] ページで、[展開] アイコンをクリックして、削除するカスタム ポリシーを展開します ([種類] ![ ](../../media/scc-expand-icon.png) 列は **[カスタム送信** スパム ポリシー] です)。

3. 展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。

4. 警告ダイアログが表示されたら、**[はい]** をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して送信スパム ポリシーを構成する

前述のように、送信スパム ポリシーは、送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。

Exchange Online PowerShell またはスタンドアロンの EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いは明白です。 **\* -HostedOutboundSpamFilterPolicy** コマンドレットを使用して送信スパム フィルター ポリシーを管理し **\* 、-HostedOutboundSpamFilterRule** コマンドレットを使用して送信スパム フィルター ルールを管理します。

- PowerShell では、最初に送信スパム フィルター ポリシーを作成し、次にルールが適用されるポリシーを識別する送信スパム フィルター ルールを作成します。
- PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの設定を個別に変更します。
- PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell を使用して送信スパム ポリシーを作成する

PowerShell で送信スパム ポリシーを作成するには、次の 2 つの手順を実行します。

1. 送信スパム フィルター ポリシーを作成します。
2. ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。

 **注**:

- 新しい送信スパム フィルター ルールを作成し、関連付けされていない既存の送信スパム フィルター ポリシーをそのルールに割り当てできます。 送信スパム フィルター ルールは、複数の送信スパム フィルター ポリシーに関連付けけれなくなります。

- ポリシーを作成するまでセキュリティ & コンプライアンス センターでは使用できない、PowerShell の新しい送信スパム フィルター ポリシーに関する次の設定を構成できます。

  - 無効な新しいポリシーを作成 `$false` します **(New-HostedOutboundSpamFilterRule** コマンドレットで有効)。
  -  _\<Number\>_ **New-HostedOutboundSpamFilterRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しい送信スパム フィルター ポリシーは、ポリシーをスパム フィルター ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する

送信スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、Contoso Executives という名前の新しい送信スパム フィルター ポリシーを次の設定で作成します。

- 受信者レートの制限は、既定値の小さい値に制限されます。 詳細については [、「Microsoft 365 のオプションでの送信の制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 制限の 1 に達すると、ユーザーはメッセージを送信できません。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

構文およびパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する

送信スパム フィルター ルールを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の設定を使用して Contoso Executives という名前の新しい送信スパム フィルター ルールを作成します。

- Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられている。

- ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

構文およびパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを表示する

すべての送信スパム フィルター ポリシーの要約リストを返す場合は、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

特定の送信スパム フィルター ポリシーに関する詳細情報を返す場合は、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

この例では、Executives という名前の送信スパム フィルター ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

構文およびパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを表示する

既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

すべての送信スパム フィルター ルールの要約リストを返す場合は、次のコマンドを実行します。

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

特定の送信スパム フィルター ルールに関する詳細情報を返す場合は、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

構文およびパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを変更する

この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) を使用して送信スパム フィルター ポリシーを作成する」セクションで説明したように、PowerShell でマルウェア フィルター ポリシーを変更する場合と同じ設定を使用できます。

> [!NOTE]
> 送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ/コンプライアンス センターで送信スパム ポリシーの名前を変更&、送信スパム フィルター ルールの名前のみを変更 _します_。

送信スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを変更する

PowerShell で送信スパム フィルター ルールを変更する場合に使用できない唯一の設定は _、_ 無効にされたルールを作成できる Enabled パラメーターです。 既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、PowerShell で送信スパム フィルター ルールを変更するときに追加の設定を使用できません。 「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。

送信スパム フィルター ルールを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを有効または無効にする

PowerShell で送信スパム フィルター ルールを有効または無効にすると、送信スパム ポリシー全体 (送信スパム フィルター ルールと割り当てられた送信スパム フィルター ポリシー) が有効または無効にされます。 既定の送信スパム ポリシーを有効または無効にできない (常にすべての受信者に適用される)。

PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ルールを無効にします。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule」](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [「Disable-HostedOutboundSpamFilterRule」](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)を参照してください。

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
> - 新しいルールを作成するときに優先度を設定するには、代わりに **New-HostedOutboundSpamFilterRule** コマンドレットの _Priority_ パラメーターを使用します。
>
> - 送信の既定のスパム フィルター ポリシーには対応するスパム フィルター ルールが設定されていないので、常に変更できない優先度の値 **が Lowest です**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを削除する

PowerShell を使用して送信スパム フィルター ポリシーを削除する場合、対応する送信スパム フィルター ルールは削除されません。

PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ポリシーを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを削除する

PowerShell を使用して送信スパム フィルター ルールを削除する場合、対応する送信スパム フィルター ポリシーは削除されません。

PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>詳細情報

[制限されたユーザー ポータルからブロックされたユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)

[自動転送済みメッセージレポート](mfi-auto-forwarded-messages-report.md)
