---
title: グループ、グループ、Microsoft 365、およびTeamsのコンプライアンス SharePointオプション
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: グループ、グループ、グループMicrosoft 365、およびTeamsのコンプライアンス オプションSharePointします。
ms.openlocfilehash: 93bf2830d29f21f2239a17b9c2e381c46e85eea1
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394614"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>グループ、グループ、Microsoft 365、およびTeamsのコンプライアンス SharePointオプション

Microsoft 365共同作業時にコンプライアンスを維持するためのツールの完全なスイートを提供しています。 これらのオプションを確認し、ビジネス ニーズ、データの感度、ユーザーが共同作業に必要なユーザーの範囲にマップする方法を検討します。

次の表に、コンプライアンス コントロールのクイック リファレンスを示します。Microsoft 365。 詳細については、次のセクションで説明します。

|カテゴリ|説明|Reference|
|:-------|:----------|:--------|
|情報の保持|||
||グループのメールとコンテンツSharePoint保持する|[SharePoint と OneDrive のアイテム保持ポリシーの詳細](../compliance/retention-policies-sharepoint.md)|
||チャットとメッセージを保持する|[Microsoft Teams のアイテム保持ポリシーの詳細](../compliance/retention-policies-teams.md)|
|情報の分類|||
||グループとチームを分類する|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||機密コンテンツを自動的に分類する|[秘密度ラベルをコンテンツに自動的に適用する](../compliance/apply-sensitivity-label-automatically.md)|
||機密性の高いコンテンツを暗号化する|[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](../compliance/encryption-sensitivity-labels.md)|
|情報保護|||
||機密情報の損失を防止する|[データ損失防止について](../compliance/dlp-learn-about-dlp.md)|
||チャット内の機密情報を保護します。|[データ損失防止と Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||組織の機密情報を定義する|[カスタムの機密情報タイプ](../compliance/sensitive-information-type-learn-about.md)|
|ユーザーのセグメント化|||
||ユーザー セグメント間の通信を制限する|[情報障壁](../compliance/information-barriers.md)|
|データ所在地|||
||特定の地域の場所にデータを保存する|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>情報の保持

アイテム保持ポリシーを使用すると、グループやチームでの共同作業に使用されるアイテム (ファイル、メッセージ、メールなど) を保持または削除できます。 ポリシーは、保持と削除、保持のみ、または削除専用に設定できます。 アイテム保持ポリシーの対象となる情報は、グループまたはチームの有効期限が切れた場合、または削除された場合に保護されます。

グループ グループのアイテム保持ポリシー Microsoft 365、グループ メールボックスと関連付けられているサイトとSharePointをカバーします。

- [SharePoint と OneDrive のアイテム保持ポリシーの詳細](../compliance/retention-policies-sharepoint.md)

チャットおよびチャネル メッセージTeams保持するアイテム保持ポリシー。 チャット メッセージとチャネル メッセージは、Exchangeメールボックスに保存されます。チャット メッセージとチャネル メッセージは、Exchange影響を受け取る必要があります。 アイテム保持ポリシーを設定して、チャットやチャネル メッセージTeams適用Teams必要があります。 

ユーザー アカウントが削除された場合でも、ユーザー チャットは無期限に保持されます。 このデータを無期限に保持しない場合は、保持ポリシーを使用して、指定した時間後にユーザー チャットを削除するか、この削除をユーザー削除プロセスに含めるか検討してください。

- [Microsoft Teams のアイテム保持ポリシーの詳細](../compliance/retention-policies-teams.md)

- [Microsoft Teams のアイテム保持ポリシー](/microsoftteams/retention-policies)

1 つのアイテム保持ポリシーを設定して、チャットやチャネル TeamsメッセージTeams適用できます。 

追加情報:

- [アイテム保持ポリシーの詳細を見る](../compliance/retention.md)

- [アイテム保持タグとアイテム保持](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)ポリシー Exchange

## <a name="information-classification"></a>情報の分類

感度ラベルを使用すると、ゲスト アクセス、グループとチームのプライバシー、グループとチームの管理されていないデバイスによるアクセスを管理できます。 ラベルを適用すると、これらの設定はラベル設定で指定された通り自動的に構成されます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

機密情報の種類の検出やトレーニング可能な分類子とのパターンマッチングなど、指定した条件に基づいてファイルや電子メールに機密ラベルを自動適用する Microsoft 365 を構成できます。

- [秘密度ラベルをコンテンツに自動的に適用する](../compliance/apply-sensitivity-label-automatically.md)

秘密度ラベルを使用してファイルを暗号化し、ファイルの暗号化を解除して読み取る権限を持つユーザーのみを許可できます。

- [秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](../compliance/encryption-sensitivity-labels.md)

- [セキュリティの分離を使用してチームを構成する](./secure-teams-security-isolation.md)

追加情報:

- [秘密度ラベルの詳細](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>情報保護

DLP ポリシーを使用すると、ユーザー、およびユーザー間でSharePoint情報Exchange共有Teams。 一連のルールに基づいて実行するアクション (アクセスのブロックなど) を指定するポリシーを作成できます。

- [データ損失防止について](../compliance/dlp-learn-about-dlp.md)

このページTeams DLP は、機密情報を含むTeamsを削除することで、チャットおよびチャネル メッセージの機密情報を保護するのに役立ちます。

- [データ損失防止と Microsoft Teams](../compliance/dlp-microsoft-teams.md)

プロジェクト コード名など、組織に固有の機密情報がある場合は、独自の機密情報の種類を作成して DLP ポリシーに適用して、グループ、チーム、および SharePoint のコンテンツを保護できます。

- [カスタムの機密情報タイプ](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>ユーザーのセグメント化

情報の障壁を利用すると、データとユーザーをセグメント化して、グループ間の望ましくないコミュニケーションとコラボレーションを制限し、組織に対する利益相反を回避できます。 情報バリアを使用すると、組織内のユーザーグループ間でのファイルの共同作業、チャット、通話、会議の招待を許可または防止するポリシーを作成できます。

- [情報障壁](../compliance/information-barriers.md)

- [Microsoft Teams の情報バリア](/microsoftteams/information-barriers-in-teams)

- [情報バリアを使用してSharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>データ所在地

複数地域Microsoft 365を使用すると、データ常駐の要件を満たすために選択した地域の場所にデータをプロビジョニングして保存できます。 複数地域環境では、Microsoft 365 テナントは中央の場所 (Microsoft 365 サブスクリプションが最初にプロビジョニングされた場所) と、データを格納できる 1 つ以上のサテライトの場所で構成されます。

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Microsoft 365 Multi-Geo の計画](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[セキュリティとコンプライアンスのExchange Online](/exchange/security-and-compliance/security-and-compliance)

[情報を保護する](../compliance/information-protection.md)
