---
title: Microsoft 365でセキュリティで保護されたファイルとドキュメントの共有とTeamsとのコラボレーションを設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: 機密に基づいてデータを保護するために、Teamsでセキュリティで保護されたファイルコラボレーションと共有を設定するためのベスト プラクティスについて説明します。
ms.openlocfilehash: 54bfe4bce20687474526916fe7b11ca0e5bb1b72
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65286540"
---
# <a name="set-up-secure-file-sharing-and-collaboration-with-microsoft-teams"></a>Microsoft Teamsでセキュリティで保護されたファイル共有とコラボレーションを設定する

ファイルやドキュメントを適切なユーザーと簡単に共有できる一方で、過剰共有を防ぐことは、組織の成功の鍵です。 これには、機密データまたはその他の機密データを、アクセス権を持つ必要があるユーザーと安全に共有できることが含まれます。 プロジェクトによっては、組織外のユーザーとの機密データの共有が含まれる場合があります。

このコラボレーション ソリューションガイダンスには、次の 2 つのコンポーネントが含まれています。

- プロジェクトごとに適切なレベルの保護を使用してTeamsをデプロイする
- プロジェクトごとに適切なセキュリティ設定を使用して外部共有を構成する

![適切な保護を使用してTeamsを展開し、適切なセキュリティ設定を使用して外部共有を構成します。](..\media\solutions-architecture-center\secure-collaboration-overview.png)

多用途で使いやすいファイル コラボレーション ツールが利用できない場合、ユーザーはドキュメントを電子メールで送信して共同作業を行うことがよくあります。 これは、面倒でエラーが発生しやすいコラボレーション方法であり、情報の不適切な共有のリスクを高めることができます。 ユーザーがファイルの共有が困難すぎる場合は、IT によって管理されていないコンシューマー製品の使用に戻る可能性があります。 これにより、さらに大きなリスクが生じる可能性があります。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Microsoft 365を使用すると、次のようなさまざまな構成でTeamsをデプロイできます。

- 知的財産を保護する
- ドキュメントやその他のファイルとの簡単なコラボレーションを有効にする
- ユーザーの満足度を高め、シャドウ IT のリスクを軽減するセキュリティと使いやすさのバランスを作成する

ほとんどの組織は、さまざまな情報を持ち、情報が不適切に共有された場合、さまざまな感度とビジネスへの影響度が異なります。 特定の情報の機密性に応じて、次の情報の共有を許可することもできます。

- すべてのユーザー (認証されていない)
- 組織内のユーザー
- 組織内の特定のユーザー
- 組織内外の特定のユーザー

マーケティング パンフレットなどの情報は、組織の外部で広く共有するためのものです。 カフェテリア メニューなどの情報は外部共有を目的としていませんが、外部で共有された場合、ビジネス上の影響はありません。 これらの種類の情報は、ほとんど、またはまったく保護する必要はありません。

開発中の同じマーケティング パンフレットは、組織内でのみ共有できます。 この場合、Teamsの既定の共有設定で十分な場合があります。

開発中の新しい製品に関する情報は、組織内であっても機密性が高いと見なされる場合があります。 この場合は、より高度な保護が適切な場合があります。 たとえば、この情報へのアクセスを特定のチームのメンバーに制限できます。 プロジェクトによっては、ベンダーやパートナー組織など、組織外のユーザーと共同作業することが必要になる場合があります。

組織の成功に不可欠な情報、または厳格なセキュリティまたはコンプライアンス要件を持つ情報では、さらに高いレベルの保護が必要になる場合があります。

![低い (リリースされたパンフレット) から高い (機密ビジネス データ) までのリスク スケール。](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

上記のすべてのシナリオでは、Microsoft Teamsのチームを使用して、情報を保存、共有、共同作業できます。

セキュリティで保護されたコラボレーションを構成するには、これらのMicrosoft 365機能と機能を使用します。

|製品またはコンポーネント|機能|ライセンス|
|---|---|---|
|Microsoft Defender for Office 365|SPO、OneDrive、Teamsの添付ファイルをセーフします。ドキュメントのセーフ;Teamsのセーフ リンク|Microsoft 365 E1、E3、E5|
|SharePoint|サイトとファイル共有ポリシー、サイト共有アクセス許可、共有リンク、アクセス要求、サイト ゲスト共有設定|Microsoft 365 E1、E3、E5|
|Microsoft Teams|ゲスト アクセス、プライベート チーム、プライベート チャネル、共有チャネル|Microsoft 365 E1、E3、E5|
|Microsoft Purview|秘密度ラベル|Microsoft 365 E3、E5|

## <a name="collaboration-governance-framework-for-teams-and-microsoft-365"></a>TeamsとMicrosoft 365のコラボレーション ガバナンス フレームワーク

Microsoft 365には、コラボレーション ソリューションを管理するための多くのオプションが用意されています。 この展開コンテンツを [コラボレーション ガバナンス コンテンツ](collaboration-governance-overview.md) と共に使用して、組織に最適なコラボレーション ソリューションを作成することをお勧めします。

### <a name="securing-teams-for-sensitive-and-highly-sensitive-data"></a>機密データと機密性の高いデータのTeamsのセキュリティ保護

さまざまな感度を持つ情報へのアクセスを管理するために、[Teams用に 3 つの異なる保護レベルを](configure-teams-three-tiers-protection.md)開発しました。 これらのレベルのいずれかをカスタマイズして、ニーズやビジネスに適切に対処できます。

![Teamsに対する 3 つのレベルの保護の図。](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)

次の表に示すように、これらの層 ( *ベースライン*、 *機密*、 *および機密性の高い* ) は、過剰共有と潜在的な情報漏えいを防ぐのに役立つ保護を徐々に強化します。

|-|基準レベル|機密レベル|機密性の高いレベル|
|---|---|---|---|
|パブリック チームまたはプライベート チーム|[Either/リンク/埋め込み]|プライベート|プライベート|
|認証されていない共有|Blocked|Blocked|Blocked|
|ファイル共有|可|可|共有できるのはチームの所有者のみです。|
|チーム メンバーシップ|誰でもパブリック チームに参加できます。<br>プライベート チームに参加するために必要なチーム所有者の承認。|参加するために必要なチーム所有者の承認。|参加するために必要なチーム所有者の承認。|
|ドキュメントの暗号化|||秘密度ラベルで使用可能|
|ゲスト共有|可|許可またはブロックできます|許可またはブロックできます|
|非管理対象デバイス|制限なし|Web 専用アクセス|Blocked|

これらの層の構成には、次の処理が含まれます。

- ゲスト アクセスチャネルとプライベート チャネルのTeamsでの設定の構成
- チームに関連付けられたSharePoint サイトで、内部とゲストの共有、アクセス要求、共有リンクの設定を構成する
- *機密性* が *高く機密性の高い* レベルの場合は、チームを分類するための秘密度ラベルを構成し、管理されていないデバイスからのゲスト共有とアクセスを制御する
- 機密性の *高い* 層の場合、機密ラベルを構成して、それが適用されるドキュメントを暗号化する

ベースライン層から始めてから、必要に *応じて機密性* の *高い機密性の高い* レベルを使用するチームを追加して、組織内の情報を保護します。 作業を開始するには、次のリソースを参照してください。

- [ベースライン保護を使用してチームを構成する](configure-teams-baseline-protection.md)
- [機密データに対する保護機能を使用してチームを構成する](configure-teams-sensitive-protection.md)
- [機密データに対する保護機能を使用してチームを構成する](configure-teams-highly-sensitive-protection.md)

組織内でも共有から追加の保護を必要とする機密性の高いプロジェクトがある場合は、チーム メンバーのみが読み取ることができるように、独自の秘密度ラベルを使用してファイルを暗号化するチームを構成できます。 詳細については、「 [セキュリティ分離を使用してチームを構成](secure-teams-security-isolation.md) する」を参照してください。

### <a name="sharing-with-people-outside-your-organization"></a>組織外のユーザーとの共有

組織 [外のユーザーと秘密度の情報を共有](collaborate-with-people-outside-your-organization.md)することが必要になる場合があります。 これは、1 人のユーザーと 1 つのドキュメントを共有することから、世界中の大規模なパートナー組織やフリーランサーと主要なプロジェクトで共同作業することまで多岐に渡ります。 Microsoft 365では、機密情報の保護に役立つ適切な保護手段を使用して、この範囲の外部共有を簡単に行うことができます。

これらのリソースは、組織外のユーザーと共同作業するための環境の設定を開始するのに役立ちます。

- フォルダーの個々のファイルを共有するために[ドキュメントで共同作業](collaborate-on-documents.md)を行います。
- [サイトで共同作業](collaborate-in-site.md)を行い、SharePoint サイトのゲストと共同作業します。
- [チーム内の](collaborate-as-team.md) ゲストと共同作業を行うためのチームとして共同作業します。
- [チャネル内の外部参加者と共同作業](/microsoft-365/solutions/collaborate-teams-direct-connect) を行い、共有チャネルで組織外のユーザーと共同作業を行います。

共有される情報の機密性に応じて、過剰共有を防ぐためのセーフガードを追加できます。 これらのリソースは、組織に必要な保護を設定するのに役立ちます。

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)
- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](share-limit-accidental-exposure.md)
- [セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md)

パートナー組織を持つ主要なプロジェクトがある場合は、 [共有チャネル](/microsoft-365/solutions/collaborate-teams-direct-connect) または [Azure エンタイトルメント管理](b2b-extranet.md) を使用して、共同作業が必要な組織外のユーザーを管理できます。

## <a name="training-for-administrators"></a>管理者向けのトレーニング

Microsoft Learn のこれらのトレーニング モジュールは、TeamsとSharePointのコラボレーション、ガバナンス、ID 機能を学習するのに役立ちます。

### <a name="teams"></a>Teams

|トレーニング: |Microsoft Teams を使用してチームの共同作業を管理する|
|---|---|
|![Teamsコラボレーション トレーニング アイコン。](../media/manage-team-collaboration-with-microsoft-teams.svg)|「Microsoft Teams を使用してチームの共同作業を管理する」では、Microsoft 365 でのチームの共同作業の中央のハブである Microsoft Teams の機能について説明します。 Teams を使用して、Office 365 アプリケーションの充実した機能を最大限に活用しながらオンプレミスとオフプレミスの両方で、デスクトップからタブレット、携帯電話までさまざまなデバイス上で組織内のチームワークとコミュニケーションを円滑に進める方法を習得できます。 Teams が、共同作業のための包括的で柔軟な環境をさまざまなアプリケーションやデバイスで提供する方法について説明します。 このラーニングパスはMicrosoft 365 認定: Teams 管理者 の認定の準備を行うことができます。<p>2 時間 17 分 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

### <a name="sharepoint"></a>SharePoint

|トレーニング: |Microsoft 365 で SharePoint を使用して共同作業する|
|---|---|
|![SharePointトレーニング アイコン。](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|「Microsoft SharePoint で共有コンテンツを管理する」では、SharePoint の特徴と機能および Microsoft 365 と連携する仕組みについて紹介します。 ハブ サイトなど、さまざまな種類の SharePoint サイトだけでなく、情報保護、レポート、監視についても説明します。 さらに、SharePoint のファイルとフォルダーの共有を使用してコラボレーションを最適化する方法、外部でファイルを共有する方法、SharePoint 管理センターで SharePoint サイトを管理する方法も説明します。 このラーニングパスはMicrosoft 365 認定: チームワーク管理者の関連付け の認定の準備を行うことができます。<p>1 時間 14 分 - ラーニング パス - 4 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

### <a name="information-protection"></a>情報保護

|トレーニング: |Microsoft 365 で企業情報を保護する|
|---|---|
|![Teams情報保護トレーニング アイコン。](../media/protect-enterprise-information-microsoft-365.svg)|組織の情報を保護することは、かつてないほど困難になっています。「Microsoft 365 で社内の情報を保護する」のラーニング パスでは、機密情報を不用意な共有や誤用から保護する方法、データを検出して分類する方法、秘密度ラベルを使用して保護する方法、損失から保護するために機密情報を監視および分析する方法について説明します。このラーニング パスは、 Microsoft 365 認定: セキュリティ管理者アソシエイト  および  Microsoft 365 認定: エンタープライズ管理エキスパート  認定の準備に役立ちます。<p>1 時間 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-security-info-overview/introduction/)

### <a name="identity-and-access"></a>ID とアクセス

|トレーニング: |Azure Active Directory で ID とアクセスを保護する|
|---|---|
|![ID とアクセスのトレーニング アイコン。](../media/protect-identity-and-access-with-microsoft-365.svg)|ID とアクセスのラーニングパスは、最新の ID およびアクセステクノロジ、認証を強化するためのツール、組織内での ID 保護のガイダンスについて説明しています。 Microsoft ID およびアクセステクノロジを使用すると、組織のIDをオンプレミスでもクラウドでも保護し、ユーザーがどこからでも安全に作業できるようになります。 このラーニングパスはMicrosoft 365 認定: セキュリティ管理者 と Microsoft 365 認定: エンタープライズ管理エキスパート の認定のための準備を行うことが出来ます。<p>2 時間 52 分 - ラーニング パス - 6 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>エンド ユーザー向けのトレーニング

これらのトレーニング モジュールは、ユーザーがMicrosoft 365での共同作業にTeams、グループ、およびSharePointを使用するのに役立ちます。

|Teams|SharePoint|
|---|---|
|![チーム トレーニング アイコンを設定してカスタマイズします。](../media/set-up-customize-team-training.png)<br>**[チームを設定してカスタマイズする](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint共有と同期のトレーニング アイコン](../media/sharepoint-share-sync-training.png)<br>**[共有と同期](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teamsファイルのアップロードと検索のトレーニング アイコン。](../media/smc-teams-upload-find-files-training.png)<br>**[ファイルのアップロードと検索](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![チームとチャネルのアイコンで共同作業を行います。](../media/teams-collaborate-channels-training.png)<br>**[チームとチャネルで共同作業する](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>イラスト

これらの図は、グループやチームがMicrosoft 365で他のサービスとやり取りする方法と、組織内でこれらのサービスを管理するのに役立つガバナンスとコンプライアンス機能を理解するのに役立ちます。

### <a name="groups-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 のグループ

IT アーキテクトが Microsoft 365 のグループについて知っておくべきこと

|**アイテム**|**説明**|
|---|---|
|[![グループインフォグラフィックのサム イメージ。](../downloads/msft-m365-groups-architecture-thumb.png)](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) <br/> [PDF](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) \|[Visio](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.vsdx) <br> 更新日:2022 年 5 月|これらの図は、さまざまな種類のグループがどのように作成および管理されているか、そしていくつかのガバナンスの推奨事項を詳述しています。|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 の Microsoft Teams と関連生産性サービス

Microsoft Teamsをリードする Microsoft 365 での生産性サービスの論理的なアーキテクチャ。

|**アイテム**|**説明**|
|---|---|
|[![Teams論理アーキテクチャポスターのサム イメージ。](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \|[Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日: 2019 年 4 月|マイクロソフトは、連携してデータ ガバナンス、セキュリティ、およびコンプライアンス機能を備えたコラボレーション エクスペリエンスを提供する、一連の生産性サービスを提供しています。 <p>この一連の図は、Microsoft Teams をはじめとする、エンタープライ ズアーキテクト向けの生産性サービスの論理アーキテクチャを概説したものです。|

## <a name="deploy-the-secure-collaboration-solution"></a>セキュリティで保護されたコラボレーション ソリューションをデプロイする

このソリューションをデプロイする準備ができたら、次の手順に進みます。

1. [Teamsに対して 3 つの異なる保護レベルを構成します](configure-teams-three-tiers-protection.md)。
2. [秘密度の情報を組織外のユーザーと共有](collaborate-with-people-outside-your-organization.md)するための設定を構成します。

## <a name="see-also"></a>関連項目

[Microsoft 365 のセキュリティに関するドキュメント](../security/index.yml)

[Microsoft Purview のドキュメント](../compliance/index.yml)

[Microsoft Teams にようこそ](/MicrosoftTeams/Teams-overview)
