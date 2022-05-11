---
title: 通信コンプライアンスでチャネル信号を検出する
description: 通信コンプライアンスを使用したチャネル信号の検出の詳細について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、コミュニケーション コンプライアンス
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
ms.openlocfilehash: 51cf52c4729a543130eac676b8732ccd2fe0a388
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319080"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>通信コンプライアンスでチャネル信号を検出する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

通信コンプライアンス ポリシーを使用すると、次の通信プラットフォームの 1 つ以上のメッセージをグループまたはスタンドアロン ソースとしてスキャンできます。 これらのプラットフォーム全体でキャプチャされた元のメッセージは、組織の [保持および保持ポリシー](/microsoft-365/compliance/information-governance)に従って元のプラットフォームの場所に保持されます。 分析と調査のために通信コンプライアンス ポリシーによって使用されるメッセージのコピーは、ユーザーが組織を離れてメールボックスが削除された場合でも、ポリシーが適用されている限り保持されます。 通信ポリシーが削除されると、ポリシーに関連付けられているメッセージのコピーも削除されます。

## <a name="microsoft-teams"></a>Microsoft Teams

パブリック とプライベートの両方のMicrosoft Teams チャネルと個々のチャットのチャット通信をスキャンできます。 Microsoft Teamsカバレッジが選択された通信コンプライアンス ポリシーにユーザーが割り当てられると、ユーザーのチャット通信は、ユーザーがメンバーであるすべてのMicrosoft Teamsで自動的に監視されます。 Microsoft Teamsカバレッジは定義済みのポリシー テンプレートに自動的に含まれ、カスタム ポリシー テンプレートで既定で選択されます。 通信コンプライアンス ポリシーの条件に一致するチャットTeams処理には最大で 48 時間かかる場合があります。

プライベート チャットとプライベート チャネルの場合、通信コンプライアンス ポリシーは [共有チャネル](/MicrosoftTeams/shared-channels) と最新の添付ファイルスキャンをサポートします。 Teamsでの共有チャネルのサポートは自動的に処理され、追加の通信コンプライアンス構成の変更は必要ありません。 次の表は、Teams チャネルをグループやユーザーと共有するときの通信コンプライアンス動作をまとめたものです。

|**シナリオ**|**通信コンプライアンスの動作**|
|:-----------|:------------------------------------|
| **内部チームとチャネルを共有する** | 通信コンプライアンス ポリシーは、スコープ内のユーザーと共有チャネル内のすべてのメッセージに適用されます |
| **外部チームとチャネルを共有する** | 通信コンプライアンス ポリシーは、内部組織内の共有チャネル内の内部スコープ内のユーザーとメッセージに適用されます |

最新の添付ファイルは、Teams メッセージに含まれる[OneDrive](/onedrive/plan-onedrive-enterprise#modern-attachments)サイトまたは[SharePoint](/sharepoint/dev/solution-guidance/modern-experience-customizations) サイトから提供されるファイルです。 テキストはこれらの添付ファイルから自動的に抽出され、自動処理と、アクティブな通信コンプライアンス ポリシーの条件と分類子との一致の可能性があります。 最新の添付ファイルの検出と処理に必要な追加の構成はありません。 テキストは、ポリシー条件に一致する添付ファイルに対してのみ抽出されます。 添付ファイルにポリシーが一致する場合でも、ポリシーが一致するメッセージの添付ファイルのテキストは抽出されません。

最新の添付ファイル スキャンは、次の種類のファイルでサポートされています。

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- テキスト (.txt)
- Portable Document Format (.pdf)

モダン添付ファイルの抽出されたテキストは、ポリシーの **[保留中** のアラート] ダッシュボードの関連付けられたメッセージに含まれます。 添付ファイルの抽出されたテキストには、添付ファイル名 (および書式拡張) と.txt拡張子として名前が付けられます。 たとえば、*ContosoBusinessPlan.docx* という名前の添付ファイルの抽出されたテキストは、ポリシーの **保留中** のアラート ダッシュボードに *ContosoBusinessPlan.docx.txt* として表示されます。

抽出された添付ファイル のテキストを選択して、[ *ソース* ] ビューと [ *プレーンテキスト* ] ビューで詳細を表示します。 確認後、コマンド バー コントロールを使用して、添付ファイルのテキストを解決またはアクションを実行できます。 また、コミュニケーション コンプライアンス レビュー プロセスの外部で、レビュー用の添付ファイルをダウンロードすることもできます。

次のグループ管理構成を使用して、Teamsの個々のユーザー チャットとチャネル通信を監視します。

- **Teams チャット通信の場合:** 個々のユーザーを割り当てるか、通信コンプライアンス ポリシーに [配布グループ](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)を割り当てます。 この設定は、ユーザーとチャットの関係が 1 対 1 または 1 対多の場合に使用できます。
- **Teams チャネル通信の場合:** 特定のユーザーを含むスキャンするすべてのMicrosoft Teams チャネルまたはMicrosoft 365 グループを通信コンプライアンス ポリシーに割り当てます。 同じユーザーを別の Microsoft Teams チャネルまたは Microsoft 365 グループに追加する場合は、これらの新しいチャネルとグループを必ずコミュニケーション コンプライアンス ポリシーに追加するようにします。 チャネルのいずれかのメンバーがポリシー内の監視対象ユーザーであり、 *受信* 方向がポリシーで構成されている場合、チャネル内で送信されるすべてのメッセージはレビューの対象となり、ポリシーが一致する可能性があります (チャネル内のユーザーが明示的に監督されていない場合でも)。 たとえば、ユーザー A はチャネルの所有者またはメンバーです。 ユーザー B とユーザー C は、同じチャネルのメンバーであり、ユーザー A のみを監視する不適切なコンテンツ ポリシーと一致する言語を使用します。ユーザー B とユーザー C は、不適切なコンテンツ ポリシーで直接監督されていない場合でも、チャネル内の会話に対してポリシー一致を作成します。 Teamsユーザー A を含むチャネルの外部にあるユーザー B とユーザー C の間の会話は、ユーザー A を含む不適切なコンテンツ ポリシーの対象になりません。チャネルの他のメンバーが明示的に監督されている場合に、チャネル メンバーを監督から除外するには、該当する通信コンプライアンス ポリシーで *[受信* 通信方向] 設定をオフにします。
- **ハイブリッド電子メール環境を使用したTeamsチャット通信の場合**:通信コンプライアンスは、Exchangeオンプレミス展開またはMicrosoft Teamsを有効にした外部電子メール プロバイダーを持つ組織のユーザーのチャット メッセージを監視できます。 監視するオンプレミスまたは外部メールボックスを持つユーザーの配布グループを作成する必要があります。 通信コンプライアンス ポリシーを作成するときに、ポリシー ウィザードで **監視対象ユーザーとグループ** の選択としてこの配布グループを割り当てます。 クラウドベースのストレージを有効にするための要件と制限事項、およびオンプレミス ユーザーに対する Teams のサポートの詳細については、「[オンプレミス ユーザーの Teams チャット データを検索する](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。

## <a name="exchange-email"></a>Exchange メール

Microsoft 365またはOffice 365 サブスクリプションの一部としてExchange Onlineでホストされているメールボックスはすべて、メッセージ スキャンの対象となります。 通信コンプライアンス ポリシーの条件に一致するメール メッセージと添付ファイルのExchange処理には約 24 時間かかる場合があります。 コミュニケーション コンプライアンスでサポートされる添付ファイルの種類は、[Exchangeメール フロー ルールのコンテンツ検査でサポートされているファイルの種類](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)と同じです。

## <a name="yammer"></a>Yammer

Yammer コミュニティ内のプライベート メッセージとパブリックな会話と関連付けられた添付ファイルをスキャンできます。 定義されたチャネルとしてYammerを含む通信コンプライアンス ポリシーにユーザーを追加すると、ユーザーがメンバーであるすべてのYammer コミュニティ間の通信がスキャン プロセスに含まれます。 通信コンプライアンス ポリシーの条件に一致するチャットと添付ファイルをYammerするには、処理に最大 24 時間かかる場合があります。 

Yammer通信と添付ファイルを監視するには、通信コンプライアンス ポリシーの[ネイティブ モード](/yammer/configure-your-yammer-network/overview-native-mode)Yammer必要があります。 ネイティブ モードでは、すべてのYammer ユーザーが Azure Active Directory (AAD) にあり、すべてのグループが Office 365 グループになり、すべてのファイルが SharePoint Online に格納されます。

## <a name="skype-for-business-online"></a>Skype for Business Online

Skype for Business Online のチャット通信と関連する添付ファイルを監視できます。 コミュニケーション コンプライアンス ポリシーの条件に一致する Skype for Business Online チャットの処理には、最大 24 時間かかる場合があります。 監視付きチャット会話は、[Skype for Business Online に保存された以前の会話](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)から提供されます。  

次のグループ管理構成を使用して、Skype for Business Online でユーザー チャットの通信を監視します。

- **Skype for Business Online チャット通信の場合**: 個々のユーザーを割り当てるか、通信コンプライアンス ポリシーに [配布グループ](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)を割り当てます。 この設定は、ユーザーとチャットの関係が 1 対 1 または 1 対多の場合に使用できます。

## <a name="third-party-sources"></a>サードパーティのソース

[Instant Bloomberg](archive-instant-bloomberg-data.md)、[Slack](archive-slack-data.md)、[Zoom](archive-zoommeetings-data.md)、携帯ショートメールなどのサードパーティのソースから、Microsoft 365組織内のメールボックスにインポートされたデータの通信をスキャンできます。 通信コンプライアンスでサポートされているコネクタの完全な一覧については、「 [サード パーティのデータをアーカイブする](archiving-third-party-data.md)」を参照してください。

通信コンプライアンス ポリシーにコネクタを割り当てる前に、Microsoft 365組織のサード パーティコネクタを構成する必要があります。 通信コンプライアンス ポリシー ウィザード **の [サード パーティソース]** セクションには、現在構成されているサードパーティコネクタのみが表示されます。
