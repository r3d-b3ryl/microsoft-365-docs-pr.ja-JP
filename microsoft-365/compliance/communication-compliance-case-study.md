---
title: ケース スタディ - Contoso 社は、Microsoft Teams、Exchange、およびコミュニケーションに関する不快言語ポリシーをすばやくYammerします
description: Contoso 社のケース スタディと、Microsoft Teams、Exchange Online、およびコミュニケーションの不快言語を監視する通信コンプライアンス ポリシーをすばやく構成する方法Yammerします。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 1b9bef180fed9c3afa3b3d8d2319a1fa0260ed14
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126596"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>ケース スタディ - Contoso 社は、Microsoft Teams、Exchange、およびコミュニケーションに関する不快言語ポリシーをすばやくYammerします

Microsoft 365 の通信コンプライアンスは、組織内の不適切なメッセージを検出、キャプチャ、および処理するのに役立つ通信リスクを最小限に抑えるのに役立ちます。 定義済みポリシーとカスタム ポリシーを使用すると、ポリシーの一致について内部通信と外部通信をスキャンして、指定されたレビュー担当者が確認できます。 レビュー担当者は、組織内のスキャンされたメール、Microsoft Teams、Yammer、またはサード パーティの通信を調査し、適切な修復アクションを実行して、組織のメッセージ標準に準拠している必要があります。

Contoso Corporation は、不快な言語を監視するポリシーをすばやく構成する必要がある、架空の組織です。 ユーザーの電子メール、Microsoft Teams、Yammer サポートに主に Microsoft 365 を使用していますが、職場のハラスメントに関する会社のポリシーを適用する新しい要件があります。 Contoso 社の IT 管理者とコンプライアンス スペシャリストは、Microsoft 365 との作業の基本を理解し、通信コンプライアンスをすばやく開始する方法に関するエンドツーエンドのガイダンスを探しています。

このケーススタディでは、不快な言語の通信を監視するための通信コンプライアンスポリシーをすばやく構成するための基本について説明します。 このガイダンスは次のとおりです。

- 手順 1 : 通信コンプライアンスの計画
- 手順 2 : Microsoft 365 での通信コンプライアンスへのアクセス
- 手順 3 : 前提条件の構成および通信コンプライアンスポリシーの作成
- 手順 4 : 警告の調査および修復

## <a name="step-1-planning-for-communication-compliance"></a>手順 1: 通信コンプライアンスの計画

Contoso IT 管理者とコンプライアンス スペシャリストは、Microsoft 365 のコンプライアンス ソリューションに関するオンライン ウェビナーに参加し、コミュニケーション コンプライアンス ポリシーが職場のハラスメントを削減するための更新された企業ポリシー要件を満たすのに役立つと決定しました。 Microsoft Teams で送信されるチャット、Yammer のプライベート メッセージとコミュニティの会話、および Exchange Online で送信された電子メール メッセージについて不快な言葉を監視する通信コンプライアンス ポリシーを作成して有効にする計画を策定しました。 計画には次のものが含まれます:

- 通信コンプライアンス機能へのアクセスが必要な IT 管理者。
- 通信ポリシーを作成および管理する必要があるコンプライアンス スペシャリスト。
- 通信コンプライアンスの警告を調査および修復する必要があるコンプライアンススペシャリストおよび他の部署 (人事、法務など) の同僚。
- 通信コンプライアンス不快言語ポリシーの対象になるユーザー。

### <a name="licensing"></a>ライセンス

最初の手順では、Contoso 社の Microsoft 365 ライセンスに通信コンプライアンス ソリューションのサポートが含まれています。 通信コンプライアンスにアクセスして使用するには、Contoso の IT 管理者は Contoso が次のいずれかを持っている必要があります。

- Microsoft 365 E5 サブスクリプション (有料版または試用版)
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 コンプライアンス アドオン
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 Insider Risk Management アドオン
- Microsoft 365 A5 サブスクリプション (有料版または試用版)
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 コンプライアンス アドオン
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 Insider Risk Management アドオン
- Microsoft 365 G5 サブスクリプション (有料版または試用版)
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 コンプライアンス アドオン
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 Insider Risk Management アドオン
- Office 365 Enterprise E5 サブスクリプション (有料版または試用版)
- Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced Compliance アドオン (新しいサブスクリプションでは使用できなくなりました。注を参照)

また、通信コンプライアンス ポリシーに含まれるユーザーに上記のいずれかのライセンスを割り当てる必要があります。

>[!IMPORTANT]
>Office 365 Advanced Compliance は、スタンドアロン サブスクリプションとして販売されなくなりました。 現在のサブスクリプションの有効期限が切れた場合、お客様は上記のいずれかのサブスクリプションに移行する必要があります。このサブスクリプションには、同じまたは追加のコンプライアンス機能が含まれている必要があります。

Contoso IT 管理者は次の手順を実行して、Contoso のライセンス サポートを確認します。

1. IT 管理者は **、Microsoft 365** 管理センターにサインイン [し https://admin.microsoft.com) 、Microsoft](https://admin.microsoft.com) **365** 管理センターの課金ライセンスに  >  **移動**  >  **します**。

2. ここでは、通信コンプライアンスのサポートを含む[](communication-compliance-configure.md#subscriptions-and-licensing)ライセンス オプションの 1 つを持っている必要があります。

![通信コンプライアンスのライセンス](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>通信コンプライアンスのアクセス許可

通信コンプライアンス機能を管理するためのアクセス許可を構成するために使用される役割グループは 5 種類です。 通信コンプライアンス **を** Microsoft 365 コンプライアンス センターのメニュー オプションとして使用し、これらの構成手順を続行するには、Contoso 管理者に *Communication Compliance Admin* の役割が割り当てられます。

Contoso 社は、 *コミュニケーション* コンプライアンス役割グループを使用して、すべての通信コンプライアンス管理者、アナリスト、調査者、および閲覧者をグループに割り当て決定しました。 これにより、Contoso 社はすばやく開始し、コンプライアンス管理の要件に最も適しています。

|**役割**|**ロール権限**|
|:-----|:-----|
| **通信コンプライアンス** | この役割グループを使用して、組織の通信コンプライアンスを 1 つのグループで管理します。 指定された管理者、アナリスト、調査者、および閲覧者のすべてのユーザー アカウントを追加すると、1 つのグループで通信コンプライアンスのアクセス許可を構成できます。 この役割グループには、すべての通信コンプライアンスのアクセス許可の役割が含まれる。 この構成は、通信コンプライアンスをすばやく開始する最も簡単な方法であり、個別のユーザー グループに対して個別のアクセス許可を定義する必要はない組織に適しています。 |
| **通信コンプライアンス管理者** | 最初に通信コンプライアンスを構成し、後で通信コンプライアンス管理者を定義済みのグループに分離するには、この役割グループを使用します。 この役割グループに割り当てられているユーザーは、通信コンプライアンス ポリシー、グローバル設定、および役割グループの割り当てを作成、読み取り、更新、および削除できます。 この役割グループに割り当てられているユーザーは、メッセージ通知を表示できません。 |
| **通信コンプライアンス アナリスト** | このグループを使用して、通信コンプライアンス アナリストとして機能するユーザーにアクセス許可を割り当てる。 この役割グループに割り当てられているユーザーは、レビュー担当者として割り当てられているポリシーの表示、メッセージ のメタデータ (メッセージ コンテンツではない) の表示、追加のレビュー担当者へのエスカレート、ユーザーへの通知の送信を行えます。 アナリストは保留中のアラートを解決できません。 |
| **通信コンプライアンス担当者** | このグループを使用して、通信コンプライアンス調査担当者として機能するユーザーにアクセス許可を割り当てる。 この役割グループに割り当てられたユーザーは、メッセージのメタデータとコンテンツの表示、追加のレビュー担当者へのエスカレート、Advanced eDiscovery ケースへのエスカレート、ユーザーへの通知の送信、アラートの解決を行えます。 |
| **通信コンプライアンス ビューアー** | このグループを使用して、通信レポートを管理するユーザーにアクセス許可を割り当てる。 この役割グループに割り当てられたユーザーは、通信コンプライアンスホーム ページ上のすべてのレポート ウィジェットにアクセスし、すべての通信コンプライアンス レポートを表示できます。 |

1. Contoso IT 管理者は **、Office 365** セキュリティ & コンプライアンス センターのアクセス許可ページにサインインします [( https://protection.office.com/permissions)](https://protection.office.com/permissions)グローバル管理者アカウントの資格情報を使用し、Microsoft 365 のロールを表示および管理するリンクを選択します)。
2. セキュリティ &**コンプライアンス** センターで、[アクセス許可]に移動し、Office 365 で役割を表示および管理するリンクを選択します。
3. 管理者は *、"Communication Compliance/通信* コンプライアンス" 役割グループを選択し、[役割グループの編集 **] を選択します**。
4. 管理者は、左側のナビゲーション ウィンドウから [ **メンバー** の選択] を選択し、[編集] を **選択します**。
5. [追加 **] を** 選択し、通信コンプライアンスの管理、調査、通知の確認を行うすべての Contoso ユーザーのチェック ボックスをオンにします。
6. 管理者が [追加] を **選択し**、[完了] を **選択します**。
7. [保存] **を** 選択して、Contoso ユーザーを役割グループに追加します。 [閉じる **] を選択** して手順を完了します。

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>手順 2: Microsoft 365 の通信コンプライアンスにアクセスする

通信コンプライアンスのアクセス許可を構成した後、通信コンプライアンス役割グループに割り当てられた Contoso IT 管理者およびコンプライアンス スペシャリストは、Microsoft 365 の通信コンプライアンス ソリューションにアクセスできます。 Contoso IT 管理者とコンプライアンス スペシャリストには、通信コンプライアンスにアクセスして新しいポリシーの作成を開始する方法がいくつかあります。

- 通信コンプライアンス ソリューションから直接開始する
- Microsoft 365 コンプライアンス センターから
- Microsoft 365 ソリューション カタログから
- Microsoft 365 管理センターから

### <a name="starting-directly-from-the-communication-compliance-solution"></a>通信コンプライアンス ソリューションから直接開始する

ソリューションにアクセスする最も簡単な方法は、通信コンプライアンス **(** ) ソリューションに直接 <https://compliance.microsoft.com/supervisoryreview> サインインする方法です。 このリンクを使用すると、Contoso IT 管理者とコンプライアンス スペシャリストが通信コンプライアンスの概要ダッシュボードに移動し、アラートの状態をすばやく確認し、定義済みのテンプレートから新しいポリシーを作成できます。

![情報コンプライアンスの概要](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンス センターから

Contoso IT 管理者とコンプライアンス スペシャリストが通信コンプライアンス ソリューションにアクセスするためのもう 1 つの簡単な方法は **、Microsoft 365** コンプライアンス センター [( . https://compliance.microsoft.com)](https://compliance.microsoft.com) サインイン後にすべてのコンプライアンス ソリューションを表示し、開始するには、**すべてを表示** を選択して、**通信コンプライアンス** ソリューションを選択すれば開始します。

![コンプライアンス センター](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Microsoft 365 ソリューション カタログから

Contoso IT 管理者とコンプライアンス スペシャリストは、Microsoft 365 ソリューション カタログを選択して通信コンプライアンス ソリューションにアクセスする選択もできます。 左側 **のナビゲーションの**  [ソリューション] セクションで [カタログ] を選択すると **、Microsoft 365** コンプライアンス センターで、すべての Microsoft 365 コンプライアンス ソリューションを一覧で表示するソリューション カタログを開きます。 インサイダー リスク管理セクション **まで** スクロールダウンすると、Contoso IT 管理者は通信コンプライアンスを選択して開始できます。 Contoso IT 管理者は、ナビゲーション コントロールに表示を使用して、通信コンプライアンス ソリューションを左側のナビゲーション ウィンドウにピン留めし、サインイン時にすばやくアクセスすることもできます。

![ソリューション カタログ](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターから

Microsoft 365 管理センターから開始するときに通信コンプライアンスにアクセスするには、Contoso IT 管理者とコンプライアンススペシャリストが Microsoft 365 管理センターにサインイン [します (Microsoft https://admin.microsoft.com)](https://admin.microsoft.com) **365** 管理センター  >  **のコンプライアンス** に移動します。

![通信コンプライアンス リンク](../media/communication-compliance-case-compliance-link.png)

このアクションは **Office 365** セキュリティ/コンプライアンス センターを開き、ページ上部のバナーに表示される **Microsoft 365** コンプライアンス センターへのリンクを選択する必要があります。

![Office 365 セキュリティ/コンプライアンス センター](../media/communication-compliance-case-scc.png)

**Microsoft 365** コンプライアンス センターで Contoso IT管理者が [すべて表示] を選択すると、コンプライアンス ソリューションの完全な一覧が表示されます。

![通信コンプライアンス メニュー](../media/communication-compliance-case-show-all.png)

[すべて表示 **] を選択** すると、Contoso IT 管理者は通信コンプライアンス ソリューションにアクセスできます。

![情報コンプライアンスの概要](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>手順 3: 前提条件を構成し、通信コンプライアンス ポリシーを作成する

通信コンプライアンス ポリシーの使用を開始するには、不快な言語を監視する新しいポリシーを設定する前に、Contoso IT 管理者が構成することが必要ないくつかの前提条件があります。 これらの前提条件の完了後、Contoso IT 管理者およびコンプライアンス スペシャリストが新しいポリシーを構成し、コンプライアンス スペシャリストは調査を開始して、生成された警告を修復することができます。

### <a name="enabling-auditing-in-microsoft-365"></a>Microsoft 365 での監査の有効化

通信コンプライアンスには、警告を表示し、レビュー担当者が行った修復処置を追跡するための監査ログが必要です。 監査ログは、定義済みの組織ポリシーに関連付けられているすべてのアクティビティの概要です。また、通信コンプライアンスポリシーに変更があった場合はいつでもその概要を示します。

Contoso IT 管理者は、[詳しい手順](turn-audit-log-search-on-or-off.md) を確認して完了し、監査を有効にします。 監査を有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。 Contoso IT 管理者は、この操作を1回だけ行う必要があります。

### <a name="configuring-yammer-tenant-for-native-mode"></a>ネイティブ Yammerテナントの構成

通信コンプライアンスでは、組織の Yammer テナントがネイティブ モードで、プライベート メッセージやパブリック コミュニティの会話で不快な言葉を監視する必要があります。

Contoso IT 管理者は [、Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode) の Yammer ネイティブ モードの概要に関する記事の情報を確認し [、「Microsoft 365](/yammer/configure-your-yammer-network/native-mode) のネイティブ モード用に Yammer ネットワークを構成する」の手順に従って移行ツールを実行します。

### <a name="setting-up-a-group-for-in-scope-users"></a>範囲内のユーザーグループの設定

Contoso コンプライアンス スペシャリストは、不快な言葉を監視する通信ポリシーに、すべてのユーザーを追加する必要があります。 各ユーザー アカウントをポリシーに個別に追加することもできますが、このポリシーのユーザーに対して **All Users** 配布グループを使用する方がはるかに簡単で、時間を節約できると判断しました。

すべての Contoso ユーザーを含む新しいグループを作成する必要があります。そのため、次の手順を実行します。

1. Contoso IT 管理者 IT 管理者は **、Microsoft 365** 管理センターにサインイン [します https://admin.microsoft.com) (Microsoft](https://admin.microsoft.com) **365** 管理センターの  >  **グループ グループに移動**  >  **します**。
2. [グループの **追加] を選択** し、ウィザードを完了して新しい *Microsoft 365* グループまたは配布グループ *を作成します*。

    ![グループ](../media/communication-compliance-case-all-employees.png)

3. 新しいグループの作成後、Contoso ユーザー全員を新しいグループに追加する必要があります。 Exchange 管理センター **を開き**[、Exchange https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp)管理 **センターの受信者グループ**  >  **に移動**  >  **します**。 Contoso IT 管理者は、メンバーシップ領域と、作成した新しい *[すべての従業員*]グループを選択し、[編集] コントロールを選択して、すべての Contoso ユーザーをウィザードの新しいグループに追加します。

    ![Exchange 管理センター](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>不快な言語を監視するポリシーの作成

すべての前提条件が完了したら、Contoso IT 管理者およびコンプライアンス スペシャリストは、不快な言語を監視するための通信コンプライアンス ポリシーを構成する準備が整います。 新しい不快な言語のポリシー テンプレートを使用して、このポリシーを簡単かつ簡単に構成できます。

1. Contoso IT 管理者およびコンプライアンス スペシャリストが **Microsoft 365 コンプライアンスセンター** にサインインし、左側のナビゲーション ウィンドウから **通信コンプライアンス** を選択します。 この操作により、通信コンプライアンス ポリシー テンプレートのクイック リンクを含む **概要** ダッシュボードが開きます。 **不快な言語のモニター** を選ぶには、テンプレートの **作業の開始** を選択します。

    ![通信コンプライアンス不快言語テンプレート](../media/communication-compliance-case-template.png)

2. ポリシー テンプレート ウィザードでは、Contoso IT 管理者およびコンプライアンス スペシャリストが協働して、 **ポリシー名**、**ユーザーまたは監督対象のグループ** および **レビュー担当者** の3つの必要なフィールドを完了します。
3. ポリシーウィザードには、既にポリシーの名前が提案されているので、IT 管理者およびコンプライアンス スペシャリストが、提案された名前を保持し、残りのフィールドにフォーカスします。 監督する *ユーザー* またはグループの [すべてのユーザー] グループを選択し、レビュー担当者フィールドのポリシーアラートを調査して修復する必要があるコンプライアンス スペシャリストを **選択** します。 ポリシーを構成し、アラート情報の収集を開始する最後の手順は、[ポリシーの作成] を **選択する手順です**。

    ![通信コンプライアンス不快言語ウィザード](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>手順 4: アラートを調査して修復する

不快な言語を監視するための通信コンプライアンス ポリシーが構成されました。次の手順では、Contoso コンプライアンス スペシャリストがポリシーにより生成された警告を調査して修復します。 ポリシーによって、すべての通信ソース チャネルの通信を完全に処理し、警告が **通知ダッシュボード** に表示されるようになるには、最大で24時間かかります。

アラートが生成されると、Contoso コンプライアンススペシャリストはワークフローの[](communication-compliance-investigate-remediate.md)指示に従って、不快な言語の問題を調査して修復します。