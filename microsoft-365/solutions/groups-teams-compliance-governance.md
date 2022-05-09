---
title: Microsoft 365 グループ、Teams、SharePoint コラボレーションのコンプライアンス オプション
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 グループ、Teams、SharePointコラボレーションのコンプライアンス オプションについて説明します。
ms.openlocfilehash: afbbc6e507d613e028f65dbc157ec2222414af8c
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939128"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 グループ、Teams、SharePoint コラボレーションのコンプライアンス オプション

Microsoft 365には、ユーザーが共同作業を行う場合にコンプライアンスを維持するための完全なツール スイートが用意されています。 これらのオプションを確認し、ビジネス ニーズに対応する方法、データの機密性、ユーザーが共同作業する必要があるユーザーの範囲を検討します。

次の表に、Microsoft 365で使用できるコンプライアンス コントロールのクイック リファレンスを示します。 詳細については、次のセクションで説明します。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|情報の保持|||
||グループのメールとSharePointコンテンツを保持する|[SharePoint と OneDrive のアイテム保持ポリシーの詳細](../compliance/retention-policies-sharepoint.md)|
||チャットとメッセージを保持する|[Microsoft Teams のアイテム保持ポリシーの詳細](../compliance/retention-policies-teams.md)|
|情報の分類|||
||グループとチームを分類する|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||機密コンテンツを自動的に分類する|[機密ラベルをコンテンツに自動的に適用する](../compliance/apply-sensitivity-label-automatically.md)|
||機密コンテンツを暗号化する|[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](../compliance/encryption-sensitivity-labels.md)|
|情報保護|||
||機密情報の損失を防ぐ|[Microsoft Purview データ損失防止についての説明](../compliance/dlp-learn-about-dlp.md)|
||チャットで機密情報を保護します。|[Microsoft Purview データ損失防止とMicrosoft Teams](../compliance/dlp-microsoft-teams.md)|
||組織の機密情報を定義する|[カスタムの機密情報タイプ](../compliance/sensitive-information-type-learn-about.md)|
|ユーザーのセグメント化|||
||ユーザー セグメント間の通信を制限する|[情報障壁](../compliance/information-barriers.md)|
|データ所在地|||
||特定の地理的な場所にデータを格納する|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>情報の保持

アイテム保持ポリシーは、グループやチームの共同作業に使用されるアイテム (ファイル、メッセージ、メールなど) を保持または削除するために使用できます。 ポリシーは、保持と削除、保持のみ、または削除のみに設定できます。 アイテム保持ポリシーの対象となる情報は、グループまたはチームが期限切れになったり、削除されたりした場合に保護されます。

Microsoft 365 グループのアイテム保持ポリシーの構成には、グループ メールボックスと、関連するSharePointサイトとファイルが含まれます。

- [SharePoint と OneDrive のアイテム保持ポリシーの詳細](../compliance/retention-policies-sharepoint.md)

チャットとチャネル メッセージを保持Teamsのアイテム保持ポリシー。 チャット メッセージとチャネル メッセージはExchangeメールボックスに格納されますが、Exchangeアイテム保持ポリシーの影響を受けられません。 Teams チャットとTeams チャネル メッセージに適用するアイテム保持ポリシーを設定する必要があります。 

ユーザー アカウントが削除された場合でも、ユーザー チャットは無期限に保持されます。 このデータを無期限に保持しない場合は、アイテム保持ポリシーを使用して、指定した時間後にユーザー チャットを削除するか、ユーザー削除プロセスにこの削除を含める方法を検討してください。

- [Microsoft Teams のアイテム保持ポリシーの詳細](../compliance/retention-policies-teams.md)

- [Microsoft Teams のアイテム保持ポリシー](/microsoftteams/retention-policies)

1 つのアイテム保持ポリシーを、Teams チャットおよびTeams チャネル メッセージに適用するように設定できます。 

追加情報:

- [アイテム保持ポリシーの詳細を見る](../compliance/retention.md)

- Exchangeの[アイテム保持タグとアイテム保持ポリシー](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="information-classification"></a>情報の分類

秘密度ラベルを使用して、ゲスト アクセス、グループとチームのプライバシー、グループとチームの非管理対象デバイスによるアクセスを管理できます。 ラベルを適用すると、これらの設定はラベル設定で指定されたとおりに自動的に構成されます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

機密情報の種類の検出やトレーニング可能な分類子とのパターン マッチングなど、指定した条件に基づいて機密ラベルをファイルや電子メールに自動適用するようにMicrosoft 365を構成できます。

- [機密ラベルをコンテンツに自動的に適用する](../compliance/apply-sensitivity-label-automatically.md)

機密ラベルを使用してファイルを暗号化し、暗号化解除と読み取りを行うアクセス許可を持つファイルのみを許可できます。

- [秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](../compliance/encryption-sensitivity-labels.md)

- [セキュリティの分離を使用してチームを構成する](./secure-teams-security-isolation.md)

追加情報:

- [機密ラベルについて詳しく見る](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>情報保護

DLP ポリシーを使用すると、SharePoint、Exchange、Teams間で機密情報が誤って共有されるのを防ぐことができます。 一連のルールに基づいて、実行するアクション (アクセスのブロックなど) を指定するポリシーを作成できます。

- [データ損失防止について](../compliance/dlp-learn-about-dlp.md)

Teamsの DLP は、機密情報を含むメッセージを削除することで、Teams チャットおよびチャネル メッセージの機密情報を保護するのに役立ちます。

- [データ損失防止と Microsoft Teams](../compliance/dlp-microsoft-teams.md)

プロジェクト コード名など、組織に固有の機密情報がある場合は、独自の機密情報の種類を作成し、DLP ポリシーに適用して、グループ、チーム、SharePointのコンテンツを保護できます。

- [カスタムの機密情報タイプ](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>ユーザーのセグメント化

情報バリアを使用すると、データとユーザーをセグメント化して、グループ間の不要な通信とコラボレーションを制限し、組織の関心の対立を回避できます。 情報バリアを使用すると、組織内のユーザーのグループ間で、ファイルコラボレーション、チャット、通話、会議の招待を許可または防止するためのポリシーを作成できます。

- [情報障壁](../compliance/information-barriers.md)

- [Microsoft Teams の情報バリア](/microsoftteams/information-barriers-in-teams)

- [SharePoint で情報バリアを使用する](/sharepoint/information-barriers)

## <a name="data-residency"></a>データ所在地

Microsoft 365 Multi-Geo を使用すると、データ所在地の要件を満たすために選択した地理的な場所に、保存データをプロビジョニングして保存できます。 複数地域環境では、Microsoft 365 テナントは、中央の場所 (Microsoft 365 サブスクリプションが最初にプロビジョニングされた場所) と、データを格納できる 1 つ以上のサテライトの場所で構成されます。

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Microsoft 365 Multi-Geo の計画](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[Exchange Onlineのセキュリティとコンプライアンス](/exchange/security-and-compliance/security-and-compliance)

[情報の保護](../compliance/information-protection.md)
