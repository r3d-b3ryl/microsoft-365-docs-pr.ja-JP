---
title: 通信コンプライアンスでチャネル信号を検出する
description: 通信コンプライアンスを使用したチャネル信号の検出の詳細について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、通信コンプライアンス
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: af6b5af33ce6d10b66489f2d49ef5ed4ec1f9310
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67469209"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>通信コンプライアンスでチャネル信号を検出する

通信コンプライアンス ポリシーを使用すると、次の通信プラットフォームの 1 つ以上のメッセージをグループまたはスタンドアロン ソースとしてスキャンできます。 これらのプラットフォーム全体でキャプチャされた元のメッセージは、組織の [保持および保持ポリシー](/microsoft-365/compliance/information-governance)に従って元のプラットフォームの場所に保持されます。 分析と調査のために通信コンプライアンス ポリシーによって使用されるメッセージのコピーは、ユーザーが組織を離れてメールボックスが削除された場合でも、ポリシーが適用されている限り保持されます。 通信ポリシーが削除されると、ポリシーに関連付けられているメッセージのコピーも削除されます。

## <a name="microsoft-teams"></a>Microsoft Teams

パブリックおよびプライベートの Microsoft Teams チャネルと個々のチャットの両方のチャット通信をスキャンできます。 ユーザーが Microsoft Teams カバレッジが選択された通信コンプライアンス ポリシーにユーザーが割り当てられると、ユーザーがメンバーであるすべての Microsoft Teams で、ユーザーのチャット通信が自動的に検出されます。 Microsoft Teams のカバレッジは、定義済みのポリシー テンプレートに自動的に含まれ、カスタム ポリシー テンプレートで既定で選択されます。 コミュニケーション コンプライアンス ポリシーの条件に一致する Teams チャットの処理には、最大で 48 時間かかる場合があります。

プライベート チャットとプライベート チャネルの場合、通信コンプライアンス ポリシーは [共有チャネル](/MicrosoftTeams/shared-channels) と最新の添付ファイルスキャンをサポートします。 Teams での共有チャネルのサポートは自動的に処理され、追加の通信コンプライアンス構成の変更は必要ありません。 次の表は、Teams チャネルをグループやユーザーと共有するときの通信コンプライアンス動作をまとめたものです。

|**シナリオ**|**通信コンプライアンスの動作**|
|:-----------|:------------------------------------|
| **内部チームとチャネルを共有する** | 通信コンプライアンス ポリシーは、スコープ内のユーザーと共有チャネル内のすべてのメッセージに適用されます |
| **外部チームとチャネルを共有する** | 通信コンプライアンス ポリシーは、内部組織内の共有チャネル内の内部スコープ内のユーザーとメッセージに適用されます |

最新の添付ファイルは、Teams メッセージに含まれる [OneDrive](/onedrive/plan-onedrive-enterprise#modern-attachments) サイトまたは [SharePoint](/sharepoint/dev/solution-guidance/modern-experience-customizations) サイトから提供されるファイルです。 テキストはこれらの添付ファイルから自動的に抽出され、自動処理と、アクティブな通信コンプライアンス ポリシーの条件と分類子との一致の可能性があります。 最新の添付ファイルの検出と処理に必要な追加の構成はありません。 テキストは、メッセージが送信された時点のポリシー条件に一致する添付ファイルに対してのみ抽出されます。 添付ファイルにポリシーが一致する場合でも、ポリシーが一致するメッセージの添付ファイルのテキストは抽出されません。

最新の添付ファイル スキャンは、次の種類のファイルでサポートされています。

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- テキスト (.txt)
- Portable Document Format (.pdf)

モダン添付ファイルの抽出されたテキストは、ポリシーの **[保留中** のアラート] ダッシュボードの関連付けられたメッセージに含まれます。 添付ファイルの抽出されたテキストには、添付ファイル名 (および書式拡張) と.txt拡張子として名前が付けられます。 たとえば、*ContosoBusinessPlan.docx* という名前の添付ファイルの抽出されたテキストは、ポリシーの **保留中** のアラート ダッシュボードに *ContosoBusinessPlan.docx.txt* として表示されます。

抽出された添付ファイル のテキストを選択して、[ *ソース* ] ビューと [ *プレーンテキスト* ] ビューで詳細を表示します。 確認後、コマンド バー コントロールを使用して、添付ファイルのテキストを解決またはアクションを実行できます。 また、コミュニケーション コンプライアンス レビュー プロセスの外部で、レビュー用の添付ファイルをダウンロードすることもできます。

Teams で個々のユーザー チャットとチャネル通信を監督するには、次のグループ管理構成を使用します。

- **Teams チャット通信の場合:** 個々のユーザーを割り当てるか、 [配布グループ](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) を通信コンプライアンス ポリシーに割り当てます。 この設定は、ユーザーとチャットの関係が 1 対 1 または 1 対多の場合に使用できます。
- **Teams チャネル通信の場合:** 特定のユーザーを含むスキャン対象のすべての Microsoft Teams チャネルまたは Microsoft 365 グループを、通信コンプライアンス ポリシーに割り当てます。 同じユーザーを別の Microsoft Teams チャネルまたは Microsoft 365 グループに追加する場合は、これらの新しいチャネルとグループを必ずコミュニケーション コンプライアンス ポリシーに追加するようにします。 チャネルのいずれかのメンバーがポリシー内の監視対象ユーザーであり、 *受信* 方向がポリシーで構成されている場合、チャネル内で送信されるすべてのメッセージはレビューの対象となり、潜在的なポリシーが一致します (明示的に監督されていないチャネル内のユーザーの場合でも)。 たとえば、ユーザー A はチャネルの所有者またはメンバーです。 ユーザー B とユーザー C は、同じチャネルのメンバーであり、ユーザー A のみを監視する不適切なコンテンツ ポリシーと一致する言語を使用します。ユーザー B とユーザー C は、不適切なコンテンツ ポリシーで直接監督されていない場合でも、チャネル内の会話に対してポリシー一致を作成します。 ユーザー A を含むチャネルの外部にあるユーザー B とユーザー C の間の Teams の会話は、ユーザー A を含む不適切なコンテンツ ポリシーの対象になりません。チャネルの他のメンバーが明示的に監督されている場合に、チャネル メンバーを監督から除外するには、該当する通信コンプライアンス ポリシーで *[受信* 通信方向] 設定をオフにします。
- **ハイブリッド電子メール環境を使用した Teams チャット通信の場合**:コミュニケーション コンプライアンスは、Exchange オンプレミス展開または Microsoft Teams を有効にした外部電子メール プロバイダーを使用している組織のユーザー向けのチャット メッセージを検出できます。 オンプレミスまたは外部のメールボックスを持つユーザーの配布グループを作成する必要があります。 通信コンプライアンス ポリシーを作成するときに、ポリシー ウィザードで **監視対象ユーザーとグループ** の選択としてこの配布グループを割り当てます。 クラウドベースのストレージを有効にするための要件と制限事項、およびオンプレミス ユーザーに対する Teams のサポートの詳細については、「[オンプレミス ユーザーの Teams チャット データを検索する](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。

## <a name="exchange-email"></a>Exchange メール

Microsoft 365 またはOffice 365 サブスクリプションの一部としてExchange Onlineでホストされているメールボックスはすべて、メッセージ スキャンの対象となります。 Exchange 電子メール メッセージと添付ファイルは、通信コンプライアンス ポリシーの条件に一致するため、処理に約 24 時間かかる場合があります。 コミュニケーション コンプライアンスでサポートされる添付ファイルの種類は、[Exchangeメール フロー ルールのコンテンツ検査でサポートされているファイルの種類](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)と同じです。

## <a name="yammer"></a>Yammer

Yammer コミュニティ内のプライベート メッセージとパブリック会話、および関連する添付ファイルをスキャンできます。 定義されたチャネルとして Yammer を含むコミュニケーション コンプライアンス ポリシーにユーザーが追加されると、ユーザーがメンバーであるすべての Yammer コミュニティ間の通信がスキャン プロセスに含まれます。 通信コンプライアンス ポリシーの条件に一致する Yammer チャットと添付ファイルの処理には、最大で 24 時間かかる場合があります。 

Yammer の通信と添付ファイルを検出するには、Yammer がネイティブ [モード](/yammer/configure-your-yammer-network/overview-native-mode) になっている必要があります。 ネイティブ モードでは、すべての Yammer ユーザーが Azure Active Directory (AAD) にあり、すべてのグループが Office 365 グループになり、すべてのファイルが SharePoint Online に格納されます。

## <a name="third-party-sources"></a>サードパーティのソース

[Instant Bloomberg](/microsoft-365/compliance/archive-instant-bloomberg-data)、[Slack](/microsoft-365/compliance/archive-slack-data)、[Zoom](/microsoft-365/compliance/archive-zoommeetings-data)、SMS などのサード パーティのソースから、Microsoft 365 組織内のメールボックスにインポートされたデータの通信をスキャンできます。 通信コンプライアンスでサポートされているコネクタの完全な一覧については、「 [サード パーティのデータをアーカイブする](/microsoft-365/compliance/archiving-third-party-data)」を参照してください。

通信コンプライアンス ポリシーにコネクタを割り当てる前に、Microsoft 365 組織のサードパーティ コネクタを構成する必要があります。 通信コンプライアンス ポリシー ウィザード **の [サード パーティソース]** セクションには、現在構成されているサードパーティコネクタのみが表示されます。
