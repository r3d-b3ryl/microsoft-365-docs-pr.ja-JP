---
title: Microsoft 365 での分離とアクセス制御
ms.author: robmazz
author: robmazz
manager: scotv
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: '概要: Microsoft 365のさまざまなアプリケーション内での分離とアクセス制御の説明。'
ms.openlocfilehash: dbb5ceb8b0e1e4ef6bb80ba2c3c771fc6d6cac5b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099391"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Microsoft 365 での分離とアクセス制御

Azure Active Directory (Azure AD) とMicrosoft 365は、数十のサービス、数百のエンティティ、数千のリレーションシップ、数万の属性を含む非常に複雑なデータ モデルを使用します。 高いレベルでは、Azure ADとサービス ディレクトリは、状態ベースのレプリケーション プロトコルを使用して同期されたテナントと受信者のコンテナーです。 Azure AD内に保持されているディレクトリ情報に加えて、各サービス ワークロードには独自のディレクトリ サービス インフラストラクチャがあります。
 
![テナント データ同期をMicrosoft 365します。](../media/office-365-isolation-tenant-data-sync.png)

このモデル内では、ディレクトリ データのソースは 1 つもありません。 特定のシステムは個々のデータを所有しますが、すべてのデータを保持するシステムは 1 つもありません。 Microsoft 365 サービスは、このデータ モデルのAzure ADと連携します。 Azure ADは、共有データの "真のシステム" です。これは、通常、すべてのサービスで使用される小規模で静的なデータです。 Microsoft 365およびAzure AD内で使用されるフェデレーション モデルは、データの共有ビューを提供します。

Microsoft 365では、物理ストレージと Azure クラウド ストレージの両方が使用されます。 Exchange Online (Exchange Online Protectionを含む) とSkype for Businessは、顧客データに独自のストレージを使用します。 SharePoint Online では、SQL ServerストレージとAzure Storageの両方が使用されるため、ストレージ レベルで顧客データを余分に分離する必要があります。

## <a name="exchange-online"></a>Exchange Online

Exchange Onlineは、メールボックス内に顧客データを格納します。 メールボックスは、メールボックス データベースと呼ばれる拡張可能Storage エンジン (ESE) データベース内でホストされます。 これには、ユーザー メールボックス、リンクされたメールボックス、共有メールボックス、パブリック フォルダー メールボックスが含まれます。 ユーザー メールボックスには、保存されたSkype for Businessコンテンツ (会話履歴など) が含まれます。

ユーザー メールボックスのコンテンツには、次のものが含まれます。

- 電子メールと電子メールの添付ファイル
- 予定表と空き時間情報
- 連絡先
- タスク
- 備考
- グループ
- 推論データ

Exchange Online内の各メールボックス データベースには、複数のテナントからのメールボックスが含まれています。 承認コードは、テナント内を含め、各メールボックスをセキュリティで保護します。 既定では、割り当てられたユーザーのみがメールボックスにアクセスできます。 メールボックスをセキュリティで保護するアクセス制御リスト (ACL) には、テナント レベルでAzure ADによって認証された ID が含まれています。 各テナントのメールボックスは、テナントの認証プロバイダーに対して認証された ID に制限されます。これには、そのテナントのユーザーのみが含まれます。 テナント A のコンテンツは、テナント A によって明示的に承認されていない限り、テナント B のユーザーが取得することはできません。

## <a name="skype-for-business"></a>Skype for Business

Skype for Businessさまざまな場所にデータを格納します。

- 接続エンドポイント、テナント ID、ダイヤル プラン、ローミング設定、プレゼンス状態、連絡先リストなどを含むユーザーとアカウントの情報は、Skype for Business Active Directory サーバー、およびさまざまなSkype for Business データベース サーバーに格納されます。 連絡先リストは、ユーザーが両方の製品で有効になっている場合はユーザーのExchange Online メールボックスに格納され、ユーザーが有効でない場合はSkype for Business サーバーに保存されます。 Skype for Business データベース サーバーはテナントごとにパーティション分割されませんが、ロールベースのアクセス制御 (RBAC) を使用してデータのマルチテナント分離が適用されます。
- 会議のコンテンツとアップロードされたデータは、分散ファイル システム (DFS) 共有に格納されます。 このコンテンツは、有効にした場合はExchange Onlineでアーカイブすることもできます。 DFS 共有はテナントごとにパーティション分割されません。 コンテンツは ACL でセキュリティで保護され、マルチテナントは RBAC を使用して適用されます。
- 通話履歴、IM セッション、アプリケーション共有、IM 履歴などのアクティビティ履歴である通話詳細レコードもExchange Onlineに格納できますが、ほとんどの通話詳細レコードは通話詳細レコード (CDR) サーバーに一時的に格納されます。 コンテンツはテナントごとにパーティション分割されませんが、RBAC を使用してマルチテナントが適用されます。

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online には、データ分離を提供するいくつかの独立したメカニズムがあります。 オブジェクトは、アプリケーション データベース内に抽象化されたコードとして格納されます。 たとえば、ユーザーがファイルを SharePoint Online にアップロードすると、ファイルは逆アセンブルされ、アプリケーション コードに変換され、複数のデータベースにまたがる複数のテーブルに格納されます。

ユーザーがデータを含むストレージに直接アクセスできる場合、コンテンツは人間またはSharePoint Online 以外のシステムには解釈できません。 これらのメカニズムには、セキュリティ アクセス制御とプロパティが含まれます。 すべてのSharePoint Online リソースは、テナント内を含め、承認コードと RBAC ポリシーによって保護されます。 リソースをセキュリティで保護するアクセス制御リスト (ACL) には、テナント レベルで認証された ID が含まれています。 テナントのオンライン データSharePoint、テナントの認証プロバイダーによって認証された ID に制限されます。

ACL に加えて、認証プロバイダー (テナント固有のAzure AD) を指定するテナント レベルのプロパティは 1 回書き込まれ、一度設定した後は変更できません。 テナントに対して認証プロバイダー テナント プロパティが設定されると、テナントに公開されている API を使用して変更することはできません。

テナントごとに一意の *SubscriptionId* が使用されます。 すべての顧客サイトはテナントによって所有され、テナントに固有の *SubscriptionId が* 割り当てられます。 サイトの *SubscriptionId* プロパティは 1 回書き込まれるので、永続的です。 テナントに割り当てられたサイトを別のテナントに移動することはできません。 *SubscriptionId* は、認証プロバイダーのセキュリティ スコープを作成するために使用されるキーであり、テナントに関連付けられています。

SharePoint Online では、コンテンツ メタデータ ストレージにSQL ServerとAzure Storageが使用されます。 コンテンツ ストアのパーティション キーは、SQLの *SiteId* です。 SQL クエリを実行する場合、SharePoint Online では、テナント レベルの *SubscriptionId* チェックの一部として検証された *SiteId が* 使用されます。

SharePoint Online では、暗号化されたファイル コンテンツが Microsoft Azure BLOB に格納されます。 各SharePoint Online ファームには独自のMicrosoft Azure アカウントがあり、Azure に保存されているすべての BLOB は、SQL コンテンツ ストアに格納されているキーを使用して個別に暗号化されます。 承認レイヤーによってコードで保護され、エンド ユーザーに直接公開されない暗号化キー。 SharePoint Online には、HTTP 要求が複数のテナントのデータの読み取りまたは書き込みを行うタイミングを検出するためのリアルタイム監視があります。 要求 ID *SubscriptionId* は、アクセスされたリソースの *SubscriptionId* に対して追跡されます。 複数のテナントのリソースにアクセスする要求は、エンド ユーザーが行わてはなりません。 マルチテナント環境でのサービス要求は、唯一の例外です。 たとえば、検索クローラーはデータベース全体のコンテンツ変更を一度にプルします。 これは通常、1 つのサービス要求で複数のテナントのサイトに対してクエリを実行します。これは効率上の理由から行われます。

## <a name="teams"></a>Teams

コンテンツ タイプに応じて、Teams データの格納方法は異なります。 

詳しくは、[Microsoft Teams アーキテクチャに関する Ignite ブレークアウト セッション](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)をご確認ください。

### <a name="core-teams-customer-data"></a>顧客データTeamsコア

テナントがオーストラリア、カナダ、欧州連合、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、アラブ首長国連邦、英国、または米国でプロビジョニングされている場合、Microsoft は、その場所内でのみ次の顧客データを保存します。

- チャット、チームとチャネルの会話、画像、ボイスメール メッセージ、連絡先をTeamsします。
- SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル。
- 職場または学校のOneDriveにアップロードされたファイル。

#### <a name="chat-channel-messages-team-structure"></a>チャット、チャネル メッセージ、チーム構造

Teamsのすべてのチームは、Microsoft 365 グループとそのSharePoint サイトとExchangeメールボックスによってサポートされています。 プライベート チャット (グループ チャットを含む)、チャネル内の会話の一部として送信されたメッセージ、およびチームとチャネルの構造は、Azure で実行されているチャット サービスに格納されます。 データは、ユーザーメールボックスとグループ メールボックス内の非表示フォルダーにも格納され、Information Protection機能が有効になります。

#### <a name="voicemail-and-contacts"></a>ボイスメールと連絡先

ボイスメールはExchangeに格納されます。 連絡先は、Exchange ベースのクラウド データ ストアに格納されます。 ExchangeとExchange ベースのクラウド ストアは、世界中のデータセンターの各地域にデータ常駐を既に提供しています。 すべてのチームのボイスメールと連絡先は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、米国の国内に保存されます。 その他のすべての国では、ファイルは、テナントのアフィニティに基づいて、米国、ヨーロッパ、またはAsia-Pacificの場所に格納されます。

#### <a name="images-and-media"></a>画像とメディア

チャットで使用されるメディア (保存されていないが、元の Giphy サービス URL への参照リンクである Giphy GIF を除く)、Giphy は Microsoft 以外のサービスです)、チャット サービスと同じ場所にデプロイされる Azure ベースのメディア サービスに格納されます。

#### <a name="files"></a>Files

チャネル内で誰かが共有するファイル (OneNoteや Wiki を含む) は、チームのSharePoint サイトに格納されます。 会議または通話中にプライベート チャットまたはチャットで共有されたファイルは、ファイルを共有するユーザーの職場または学校アカウントのOneDriveにアップロードされ、保存されます。 Exchange、SharePoint、およびOneDriveは、世界中の各データセンターの地理的なデータ所在地を既に提供しています。 そのため、既存の顧客の場合、Teams エクスペリエンスの一部であるすべてのファイル、OneNote ノートブック、Teams wiki コンテンツ、メールボックスは、テナントのアフィニティに基づいて既に場所に格納されます。 ファイルは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む) の国内に保存されます。 その他のすべての国では、テナントのアフィニティに基づいて、ファイルは米国、ヨーロッパ、またはアジア太平洋の場所に格納されます。
