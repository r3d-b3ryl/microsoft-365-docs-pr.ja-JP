---
title: 通信コンプライアンスを使用してチャネル信号を検出する
description: 通信コンプライアンスを使用してチャネル信号を検出する方法について詳しくは、次の情報を参照してください。
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
ms.openlocfilehash: 9bbc79b82933c0e1586acbd08fa4e5792f949863
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335709"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>通信コンプライアンスを使用してチャネル信号を検出する

通信コンプライアンス ポリシーを使用すると、グループとして、またはスタンドアロン ソースとして、次の 1 つ以上の通信プラットフォームでメッセージをスキャンできます。 これらのプラットフォーム全体でキャプチャされた通信は、ユーザーが組織を離れ、メールボックスが削除された場合でも、既定ではポリシーごとに 7 年間保持されます。

## <a name="microsoft-teams"></a>Microsoft Teams

パブリック チャネルとプライベート チャットチャネルの両方Microsoft Teamsチャット通信をスキャンできます。 Microsoft Teams カバレッジが選択された通信コンプライアンス ポリシーにユーザーが割り当てられている場合、ユーザーのチャット通信は、ユーザーがメンバーであるすべての Microsoft Teams で自動的に監視されます。 Microsoft Teamsは、定義済みのポリシー テンプレートに自動的に含まれており、カスタム ポリシー テンプレートで既定で選択されます。 Teamsコンプライアンス ポリシーの条件に一致するチャットの処理には、最大 48 時間かかる場合があります。

プライベート チャットとプライベート チャネルの場合、通信コンプライアンス ポリシーはモダンな添付ファイルのスキャンをサポートします。 最新の添付ファイルは、OneDrive[またはSharePoint](/onedrive/plan-onedrive-enterprise#modern-attachments)[に含](/sharepoint/dev/solution-guidance/modern-experience-customizations)まれるサイトからソースTeamsです。 これらの添付ファイルからテキストが自動的に抽出され、自動処理が行われます。また、アクティブな通信コンプライアンス ポリシー条件や分類子との一致が考えらされます。 モダン添付ファイルの検出と処理に必要な追加の構成はありません。 テキストは、ポリシー条件に一致する添付ファイルにのみ抽出されます。 ポリシーが一致するメッセージの添付ファイルについては、添付ファイルにポリシーの一致がある場合でも、テキストは抽出されません。

最新の添付ファイルのスキャンは、次の種類のファイルでサポートされています。

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- テキスト (.txt)
- Portable Document Format (.pdf)

モダン添付ファイルの抽出されたテキストは、ポリシーの保留中の通知ダッシュボードに関連付けられたメッセージに含まれます。 添付ファイルの抽出されたテキストの名前は、添付ファイル名 (および形式の拡張子) と拡張子.txtされます。 たとえば、ContosoBusinessPlan.docxという名前の添付ファイルの抽出されたテキストは、ContosoBusinessPlan.docx.txtの保留中の通知ダッシュボードに表示されます。 

抽出された添付ファイル テキストを選択して、[ソース]ビュー 、[プレーン テキスト] ビュー、または [注釈] ビューで詳細 *を表示* します。 確認後、コマンド バー コントロールを使用して添付ファイルテキストを解決または処理できます。 また、コミュニケーション コンプライアンス レビュー プロセスの外部でレビュー用の添付ファイルをダウンロードすることもできます。

次のグループ管理構成を使用して、個々のユーザー チャットとチャネル通信を監視Teams。

- **チャットTeamsの場合:** 個々のユーザーを割り当てるか、[配布グループを通信](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)コンプライアンス ポリシーに割り当てる。 この設定は、ユーザーとチャットの関係が 1 対 1 または 1 対多の場合に使用できます。
- **チャネルTeamsの場合:** 特定のMicrosoft TeamsをMicrosoft 365するすべてのチャネルまたはグループを通信コンプライアンス ポリシーに割り当てる。 同じユーザーを別の Microsoft Teams チャネルまたは Microsoft 365 グループに追加する場合は、これらの新しいチャネルとグループを必ずコミュニケーション コンプライアンス ポリシーに追加するようにします。 チャネルのメンバーがポリシー内の監視対象ユーザーであり、受信方向がポリシーで構成されている場合、チャネル内で送信されるメッセージはすべて、(明示的に監督されていないチャネル内のユーザーの場合でも) 確認および潜在的なポリシー一致の対象となります。 たとえば、ユーザー A はチャネルの所有者またはメンバーです。 ユーザー B とユーザー C は、同じチャネルのメンバーであり、ユーザー A のみを監督する不快な言語ポリシーと一致する言語を使用します。ユーザー B とユーザー C は、攻撃的な言語ポリシーで直接監督されていない場合でも、チャネル内の会話に対してポリシー一致を作成します。 Teams A を含むチャネルの外部にあるユーザー B とユーザー C の間の会話は、ユーザー A を含む不快な言語ポリシーの対象とならなくなっています。チャネルの他のメンバーが明示的に監督されている場合にチャネル メンバーを監督から除外するには、該当する通信コンプライアンス ポリシーの [受信通信方向] 設定をオフにします。
- **ハイブリッドTeams** チャット通信の場合: 通信コンプライアンスは、Exchange オンプレミス展開の組織または Microsoft Teams を有効にした外部メール プロバイダーのユーザーのチャット メッセージを監視できます。 監視するには、オンプレミスまたは外部メールボックスを持つユーザーの配布グループを作成する必要があります。 通信コンプライアンス ポリシーを作成する場合は、ポリシー ウィザードでこの配布グループを [監視対象ユーザーとグループ] **の選択** として割り当てる必要があります。 クラウドベースのストレージを有効にするための要件と制限事項、およびオンプレミス ユーザーに対する Teams のサポートの詳細については、「[オンプレミス ユーザーの Teams チャット データを検索する](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。

## <a name="exchange-email"></a>Exchange メール

サブスクリプションの一Exchange Onlineとしてホストされているメールボックスは、Microsoft 365またはOffice 365スキャンの対象となります。 Exchangeポリシーの条件に一致する電子メール メッセージと添付ファイルの処理には、最大で 24 時間かかる場合があります。 コミュニケーション コンプライアンスでサポートされる添付ファイルの種類は、[Exchangeメール フロー ルールのコンテンツ検査でサポートされているファイルの種類](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)と同じです。

## <a name="yammer"></a>Yammer

プライベート メッセージとパブリック会話、および関連付Yammerコミュニティでスキャンできます。 Yammer を定義されたチャネルとして含む通信コンプライアンス ポリシーにユーザーを追加すると、ユーザーがメンバーであるすべての Yammer コミュニティ間の通信がスキャン プロセスに含まれます。 Yammerコンプライアンス ポリシーの条件に一致するチャットと添付ファイルの処理には、最大で 24 時間かかる場合があります。 

Yammerおよび添付[ファイルを監視](/yammer/configure-your-yammer-network/overview-native-mode)するには、通信コンプライアンス ポリシーのネイティブ モードYammer必要があります。 ネイティブ モードでは、すべての Yammer ユーザーが Azure Active Directory (AAD)、すべてのグループが Office 365 グループであり、すべてのファイルが SharePoint Online に保存されます。

## <a name="skype-for-business-online"></a>Skype for Business Online

オンラインでのチャット通信と関連付Skype for Businessの監視が可能です。 コミュニケーション コンプライアンス ポリシーの条件に一致する Skype for Business Online チャットの処理には、最大 24 時間かかる場合があります。 監視されたチャットの会話は、オンラインで保存された以前の会話[Skype for Businessされます](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  

次のグループ管理構成を使用して、オンラインでのユーザー チャット通信Skype for Businessします。

- **オンライン チャットSkype for Business:** 個々のユーザーを割り当てるか、または配布グループを通信コンプライアンス [ポリシーに](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)割り当てる。 この設定は、ユーザーとチャットの関係が 1 対 1 または 1 対多の場合に使用できます。

## <a name="third-party-sources"></a>サードパーティのソース

インスタント ブルームバーグ、Slack、Zoom、SMS、その他多くのサードパーティソースから、Microsoft 365 組織のメールボックスにインポートされたデータ[](archive-slack-data.md)の通信[](archive-zoommeetings-data.md)をスキャンできます。 [](archive-instant-bloomberg-data.md) 通信コンプライアンスでサポートされるコネクタの完全な一覧については、「サードパーティのデータをアーカイブ [する」を参照してください](archiving-third-party-data.md)。

通信コンプライアンス ポリシーにコネクタを割り当てる前に、Microsoft 365組織のサード パーティ製コネクタを構成する必要があります。 通信 **コンプライアンス ポリシー ウィザードの [** サード パーティのソース] セクションには、現在構成されているサード パーティ コネクタだけが表示されます。
