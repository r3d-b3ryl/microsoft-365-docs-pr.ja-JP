---
title: ケーススタディ-Contoso 社は、Microsoft Teams、Exchange、Yammer の通信に対して、不快な言語ポリシーを迅速に構成します。
description: Contoso 社のケーススタディと、Microsoft Teams、Exchange Online、Yammer の通信で不快な言葉を監視するために、コミュニケーションコンプライアンスポリシーを迅速に構成する方法について説明します。
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
ms.openlocfilehash: 79948e514009d3adffcead87aafc18ab2f1e3b25
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597636"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>ケーススタディ-Contoso 社は、Microsoft Teams、Exchange、Yammer の通信に対して、不快な言語ポリシーを迅速に構成します。

Microsoft 365 の通信コンプライアンスは、組織内の不適切なメッセージを検出、取得、および処理できるようにすることによって、通信リスクを最小限に抑えるのに役立ちます。 定義済みおよびカスタムのポリシーを使用すると、ポリシーの一致に関する内部通信と外部通信をスキャンして、指定したレビュー担当者がそれらを調査できるようにすることができます。 レビューアーは、スキャンされた電子メール、Microsoft Teams、Yammer、または組織内のサードパーティの通信を調査し、適切な修復処置を行って、組織のメッセージ標準に準拠していることを確認できます。

Contoso Corporation は、不快な言語を監視するポリシーをすばやく構成する必要がある、架空の組織です。 ユーザーは Microsoft 365 を主に電子メール、Microsoft Teams、Yammer のサポートに使用していましたが、workplace 嫌がらせに関して会社のポリシーを適用するための新しい要件があります。 Contoso 社の IT 管理者およびコンプライアンスの専門家は、Microsoft 365 の使用に関する基本事項について基本的な理解を深めており、コミュニケーションのコンプライアンスをすばやく始める方法についてのエンドツーエンドのガイダンスを求めています。

このケーススタディでは、不快な言語の通信を監視するための通信コンプライアンスポリシーをすばやく構成するための基本について説明します。 このガイダンスは次のとおりです。

- 手順 1 : 通信コンプライアンスの計画
- 手順 2 : Microsoft 365 での通信コンプライアンスへのアクセス
- 手順 3 : 前提条件の構成および通信コンプライアンスポリシーの作成
- 手順 4 : 警告の調査および修復

## <a name="step-1-planning-for-communication-compliance"></a>手順 1: 通信のコンプライアンスを計画する

Contoso 社の IT 管理者およびコンプライアンスの専門家は、Microsoft 365 のコンプライアンスソリューションに関するオンラインウェビナーに参加しており、コミュニケーションコンプライアンスポリシーが、workplace 嫌がらせを削減するために更新された企業ポリシー要件を満たすのを支援することを決定しました。 共同作業では、Microsoft Teams で送信されるチャット、Yammer のプライベートメッセージ、コミュニティの会話、Exchange Online で送信された電子メールメッセージなどを監視するための、通信コンプライアンスポリシーを作成し、有効にするための計画が策定されました。 計画には次のものが含まれます:

- 通信コンプライアンス機能にアクセスする必要がある IT 管理者。
- コミュニケーションポリシーを作成および管理する必要があるコンプライアンススペシャリスト。
- コミュニケーションのコンプライアンス警告を調査および修復する必要がある、他の部門 (人事、法律など) のコンプライアンススペシャリストおよびその他の仕事仲間。
- 通信コンプライアンス不快な言語ポリシーの範囲内となるユーザー。

### <a name="licensing"></a>ライセンス

最初の手順は、Contoso 社の Microsoft 365 ライセンスに、コミュニケーションコンプライアンスソリューションのサポートが含まれていることを確認することです。 通信コンプライアンスにアクセスして使用するために、Contoso 社の IT 管理者は Contoso に次のいずれかの情報が含まれていることを確認する必要があります。

- Microsoft 365 E5 サブスクリプション (有料または試用版)
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 コンプライアンスアドオン
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 Insider リスク管理アドオン
- Microsoft 365 A5 サブスクリプション (有料または試用版)
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 コンプライアンスアドオン
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 Insider リスク管理アドオン
- Microsoft 365 G5 サブスクリプション (有料または試用版)
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 コンプライアンスアドオン
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 Insider リスク管理アドオン
- Office 365 Enterprise E5 サブスクリプション (有料または試用版)
- Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced コンプライアンスアドオン (新しいサブスクリプションでは使用できなくなりました)。メモを参照してください。

また、通信コンプライアンスポリシーに含まれているユーザーに上記のいずれかのライセンスを割り当てる必要があることも確認する必要があります。

>[!IMPORTANT]
>Office 365 Advanced コンプライアンスは、スタンドアロンサブスクリプションとして販売されなくなりました。 現在のサブスクリプションの有効期限が切れた場合、お客様は上記のサブスクリプションのいずれかに移行する必要があります。これには、同じまたは追加のコンプライアンス機能が含まれます。

Contoso 社の IT 管理者は、次の手順を実行して Contoso のライセンスサポートを確認します。

1. IT 管理者は、 **microsoft 365 管理センター** [ https://admin.microsoft.com) にサインインして](https://admin.microsoft.com)、 **microsoft 365 管理センター**  >  **請求**  >  **ライセンス**に移動します。

2. ここでは、通信コンプライアンスのサポートを含む[ライセンスオプション](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin)の1つを持っていることを確認します。

![コミュニケーションコンプライアンスライセンス](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>通信コンプライアンスのアクセス許可

通信コンプライアンス機能を管理するためのアクセス許可を構成するために使用する役割は5つあります。 Microsoft 365 コンプライアンスセンターで通信のコンプライアンスをメニューオプションとして利用できるようにし、これらの構成手順を続行するために、Contoso 管理者には*通信コンプライアンス管理者*の役割が割り当てられます。

Contoso 社は、1つの custome 役割グループを作成し、すべての通信コンプライアンスの役割をそのグループに割り当てることを決定しています。 これにより、Contoso はすぐに迅速に開始し、コンプライアンス管理要件に最適なものにすることができます。

Contoso 社は、次のすべての通信コンプライアンス役割を含む1つの役割グループを作成します。

|**役割**|**ロール権限**|
|:-----|:-----|
| **コミュニケーションコンプライアンス管理者** | この役割を割り当てられたユーザーは、通信コンプライアンスポリシー、グローバル設定、および役割グループの割り当てを作成、読み取り、更新、および削除できます。 この役割を割り当てられたユーザーは、メッセージ通知を表示できません。 |
| **コミュニケーションコンプライアンスの分析** | この役割を割り当てられたユーザーは、レビューアーとして割り当てられたポリシーを表示したり、メッセージのメタデータを表示したり、追加のレビュー担当者にエスカレートしたり、ユーザーに通知を送信したりできます。 アナリストは保留中の通知を解決できません。 |
| **コミュニケーションコンプライアンスの調査** | この役割を割り当てられたユーザーは、メッセージのメタデータとコンテンツを表示したり、追加のレビュー担当者にエスカレートしたり、高度な電子情報開示ケースにエスカレートしたり、ユーザーに通知を送信したり、アラートを解決したりできます。 |
| **通信コンプライアンスビューアー** | この役割を割り当てられたユーザーは、コミュニケーションコンプライアンスのホームページにあるすべてのレポート作成ウィジェットにアクセスでき、すべての通信コンプライアンスレポートを表示できます。 |
| **コミュニケーションコンプライアンスケースの管理** | この役割を割り当てられたユーザーは、ケースを管理し、通知を操作できます。 この役割は、管理者、アナリスト、および調査担当者に対してカスタムの役割グループを作成するときに必要になります。 閲覧者のカスタムグループには、この役割を割り当てる必要はありません。 |

1. Contoso IT 管理者は、 **Office 365 セキュリティとコンプライアンスセンター**のアクセス許可ページにサインインします[( https://protection.office.com/permissions) ](https://protection.office.com/permissions)グローバル管理者アカウントの資格情報を使用して、Microsoft 365 の役割を表示および管理するためのリンクを選択します)。
2. [**作成**] を選択すると、新しい役割グループに [*通信コンプライアンス*] のフレンドリ名が与えられ、[**次へ**] を選択します。
3. **役割の選択** を選択し、 **追加** を選択します。 *コミュニケーションコンプライアンス管理者*、*コミュニケーションコンプライアンス分析*、*コミュニケーションコンプライアンスの調査*、*コミュニケーション*のコンプライアンス閲覧者、および*コミュニケーションコンプライアンスのケース管理*のチェックボックスをオンにして、必要な役割を追加し、[**追加**]、[**完了]、** [**次へ**] を選択します。

    ![コミュニケーションコンプライアンスの役割](../media/communication-compliance-case-roles.png)

4. 次に、IT 管理者は、 **メンバーの選択** に続いて **追加** を選択します。 ポリシーを作成するすべてのユーザーとグループのチェックボックスをオンにして、ポリシーの一致でメッセージを管理します。 IT 管理者、コンプライアンス スペシャリスト、およびその他の同僚を、初期計画で指定された人事および法務部門に追加し、**追加**、**完了** および **次へ** を選択します。
5. アクセス許可を最終処理するには、IT 管理者が **役割グループの作成** を選択して終了します。 Contoso 社の Microsoft 365 サービスで役割が有効になるまで30分ほどかかります。

    ![コミュニケーションコンプライアンスレビュー](../media/communication-compliance-case-review.png)

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>手順 2: Microsoft 365 で通信のコンプライアンスにアクセスする

通信コンプライアンスのためのアクセス許可を構成した後、新しい役割グループで定義された Contoso IT 管理者およびコンプライアンス スペシャリストは、Microsoft 365 の通信コンプライアンス ソリューションにアクセスできます。 Contoso 社の IT 管理者およびコンプライアンスの専門家は、コミュニケーションへのコンプライアンスにアクセスし、新しいポリシーの作成を開始するためのいくつかの方法を備えています。

- コミュニケーションコンプライアンスソリューションから直接開始する
- Microsoft 365 コンプライアンスセンターからの開始
- Microsoft 365 ソリューションカタログからの開始
- Microsoft 365 管理センターから開始する

### <a name="starting-directly-from-the-communication-compliance-solution"></a>コミュニケーションコンプライアンスソリューションから直接開始する

ソリューションにアクセスする最も簡単な方法は、**コミュニケーションコンプライアンス**() ソリューションに直接サインインすることです <https://compliance.microsoft.com/supervisoryreview> 。 このリンクを使用すると、Contoso IT 管理者とコンプライアンスの専門家は、通知の状態をすばやく確認し、定義済みのテンプレートから新しいポリシーを作成できる、コミュニケーションコンプライアンスの概要ダッシュボードに送られます。

![情報コンプライアンスの概要](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンスセンターからの開始

Contoso IT 管理者とコンプライアンス担当者がコミュニケーションコンプライアンスソリューションにアクセスするもう1つの簡単な方法は、 **Microsoft 365 コンプライアンスセンター** [( https://compliance.microsoft.com) ](https://compliance.microsoft.com)) に直接サインインすることです。 サインイン後にすべてのコンプライアンス ソリューションを表示し、開始するには、**すべてを表示** を選択して、**通信コンプライアンス** ソリューションを選択すれば開始します。

![コンプライアンスセンター](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Microsoft 365 ソリューションカタログからの開始

Contoso 社の IT 管理者およびコンプライアンス担当者は、Microsoft 365 ソリューションカタログを選択して、コミュニケーションコンプライアンスソリューションにアクセスすることもできます。 **Microsoft 365 コンプライアンスセンター**で、左側のナビゲーションの [**ソリューション**の**カタログ**] セクションを選択すると、すべての microsoft 365 コンプライアンスソリューションを一覧表示したソリューションカタログを開くことができます。 「 **Insider リスク管理**」セクションまでスクロールすると、Contoso IT 管理者は通信のコンプライアンスを選択して開始することができます。 Contoso 社の IT 管理者は、[ナビゲーションに表示] コントロールを使用して、コミュニケーションコンプライアンスソリューションを左側のナビゲーションウィンドウにピン留めし、今後のサインイン時にすばやくアクセスできるようにすることも決定します。

![ソリューションカタログ](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターから開始する

Microsoft 365 管理センターから開始して通信コンプライアンスにアクセスするには、Contoso IT 管理者とコンプライアンス担当者が microsoft 365[管理 https://admin.microsoft.com) センターに](https://admin.microsoft.com)サインインし、 **microsoft 365 管理センター**  >  **コンプライアンス**に移動します。

![通信コンプライアンスリンク](../media/communication-compliance-case-compliance-link.png)

この操作により、 **Office 365 セキュリティ/コンプライアンスセンター**が開き、ページ上部のバナーで提供される**Microsoft 365 コンプライアンスセンター**へのリンクを選択する必要があります。

![Office 365 セキュリティ/コンプライアンスセンター](../media/communication-compliance-case-scc.png)

**Microsoft 365 コンプライアンスセンター**では、Contoso IT 管理者は [**すべて表示**] を選択して、コンプライアンスソリューションの完全な一覧を表示します。

![通信コンプライアンスメニュー](../media/communication-compliance-case-show-all.png)

[**すべて表示**] を選択すると、Contoso IT 管理者はコミュニケーションコンプライアンスソリューションにアクセスできるようになります。

![情報コンプライアンスの概要](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>手順 3: 前提条件を構成し、通信コンプライアンスポリシーを作成する

通信コンプライアンス ポリシーの使用を開始するには、不快な言語を監視する新しいポリシーを設定する前に、Contoso IT 管理者が構成することが必要ないくつかの前提条件があります。 これらの前提条件の完了後、Contoso IT 管理者およびコンプライアンス スペシャリストが新しいポリシーを構成し、コンプライアンス スペシャリストは調査を開始して、生成された警告を修復することができます。

### <a name="enabling-auditing-in-microsoft-365"></a>Microsoft 365 で監査を有効にする

通信コンプライアンスには、警告を表示し、レビュー担当者が行った修復処置を追跡するための監査ログが必要です。 監査ログは、定義済みの組織ポリシーに関連付けられているすべてのアクティビティの概要です。また、通信コンプライアンスポリシーに変更があった場合はいつでもその概要を示します。

Contoso IT 管理者は、[詳しい手順](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) を確認して完了し、監査を有効にします。 監査を有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。 Contoso IT 管理者は、この操作を1回だけ行う必要があります。

### <a name="configuring-yammer-tenant-for-native-mode"></a>ネイティブモードで Yammer テナントを構成する

通信のコンプライアンスを行うには、組織の Yammer テナントがネイティブモードになっていることが必要です。これは、プライベートメッセージやパブリックコミュニティの会話で不快な言葉を監視するためです。

Contoso 社の IT 管理者は、 [microsoft 365 記事の Yammer ネイティブモードの概要](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)に記載されている情報を確認し、「 [Microsoft 365 のネイティブモード用に Yammer ネットワークを構成](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)する」の手順に従って移行ツールを実行します。

### <a name="setting-up-a-group-for-in-scope-users"></a>範囲内のユーザーグループの設定

Contoso 社のコンプライアンス担当者が、不快な言葉を監視するコミュニケーションポリシーにすべてのユーザーを追加することを希望しています。 各ユーザーアカウントをポリシーに個別に追加することもできますが、これはより簡単になり、このポリシーのユーザーに対して**すべてのユーザー**配布グループを使用する時間が節約できることが決定されました。

すべての Contoso ユーザーを含めるために新しいグループを作成する必要があるので、次の手順を実行します。

1. Contoso it 管理者は、 **microsoft 365 管理センター** [ https://admin.microsoft.com) にサインインして](https://admin.microsoft.com)、 **microsoft 365 管理センター**  >  **グループ**  >  **グループ**に移動します。
2. [**グループの追加**] を選択し、ウィザードを完了して、新しい*Microsoft 365 グループ*または*配布グループ*を作成します。

    ![グループ](../media/communication-compliance-case-all-employees.png)

3. 新しいグループの作成後、Contoso ユーザー全員を新しいグループに追加する必要があります。 **Exchange 管理センター** [ https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)を開き、 **exchange 管理センター**の [  >  **受信者**グループ] に移動し  >  **groups**ます。 Contoso IT 管理者は、メンバーシップ領域および作成した新しい*すべての従業員*グループを選択し、[**編集**] コントロールを選択して、すべての Contoso ユーザーをウィザードの新しいグループに追加します。

    ![Exchange 管理センター](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>不快な言語を監視するポリシーの作成

すべての前提条件が完了したら、Contoso IT 管理者およびコンプライアンス スペシャリストは、不快な言語を監視するための通信コンプライアンス ポリシーを構成する準備が整います。 新しい不快な言語のポリシー テンプレートを使用して、このポリシーを簡単かつ簡単に構成できます。

1. Contoso IT 管理者およびコンプライアンス スペシャリストが **Microsoft 365 コンプライアンスセンター** にサインインし、左側のナビゲーション ウィンドウから **通信コンプライアンス** を選択します。 この操作により、通信コンプライアンス ポリシー テンプレートのクイック リンクを含む **概要** ダッシュボードが開きます。 **不快な言語のモニター** を選ぶには、テンプレートの **作業の開始** を選択します。

    ![コミュニケーションコンプライアンス不快な言語テンプレート](../media/communication-compliance-case-template.png)

2. ポリシー テンプレート ウィザードでは、Contoso IT 管理者およびコンプライアンス スペシャリストが協働して、 **ポリシー名**、**ユーザーまたは監督対象のグループ** および **レビュー担当者** の3つの必要なフィールドを完了します。
3. ポリシーウィザードには、既にポリシーの名前が提案されているので、IT 管理者およびコンプライアンス スペシャリストが、提案された名前を保持し、残りのフィールドにフォーカスします。 **ユーザーまたはグループ**の [監督] フィールドで [*すべてのユーザー* ] グループを選択し、[**レビュー担当者**] フィールドのポリシー通知を調査および修復する必要があるコンプライアンススペシャリストを選択します。 ポリシーを構成して通知情報の収集を開始するための最後の手順として、[**ポリシーの作成**] を選択します。

    ![通信コンプライアンス不快な言語ウィザード](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>手順 4: 通知を調べて修復する

不快な言語を監視するための通信コンプライアンス ポリシーが構成されました。次の手順では、Contoso コンプライアンス スペシャリストがポリシーにより生成された警告を調査して修復します。 ポリシーによって、すべての通信ソース チャネルの通信を完全に処理し、警告が **通知ダッシュボード** に表示されるようになるには、最大で24時間かかります。

通知が生成された後、Contoso 社のコンプライアンス担当者は[ワークフローの指示](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate)に従って、不快な言葉の問題を調査および修復します。