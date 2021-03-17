---
title: Microsoft 365 グループ、Teams、および SharePoint コラボレーションのコンプライアンス オプション
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
description: Microsoft 365 グループ、Teams、および SharePoint コラボレーションのコンプライアンス オプションについて説明します。
ms.openlocfilehash: f68381ab45e74b9b7c8f44465387add82bd4150a
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838653"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 グループ、Teams、および SharePoint コラボレーションのコンプライアンス オプション

Microsoft 365 には、ユーザーの共同作業に合ったコンプライアンスを維持するためのツールが用意されています。 これらのオプションを確認し、ビジネス ニーズ、データの感度、ユーザーが共同作業に必要なユーザーの範囲にマップする方法を検討します。

次の表に、Microsoft 365 で使用できるコンプライアンスコントロールのクイック リファレンスを示します。 詳細については、次のセクションで説明します。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|情報の保持|||
||グループ メールと SharePoint コンテンツを保持する|[SharePoint と OneDrive のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||チャットとメッセージを保持する|[Microsoft Teams のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|情報の分類|||
||グループとチームを分類する|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||機密コンテンツを自動的に分類する|[秘密度ラベルをコンテンツに自動的に適用する](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||機密性の高いコンテンツを暗号化する|[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|情報保護|||
||機密情報の損失を防止する|[データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||チャット内の機密情報を保護します。|[データ損失防止と Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||組織の機密情報を定義する|[カスタムの機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|ユーザーのセグメント化|||
||ユーザー セグメント間の通信を制限する|[情報障壁](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>情報の保持

アイテム保持ポリシーを使用すると、グループやチームでの共同作業に使用されるアイテム (ファイル、メッセージ、メールなど) を保持または削除できます。 ポリシーは、保持と削除、保持のみ、または削除専用に設定できます。 アイテム保持ポリシーの対象となる情報は、グループまたはチームの有効期限が切れた場合、または削除された場合に保護されます。

Microsoft 365 グループのアイテム保持ポリシーを構成するには、グループ メールボックスと、関連付けられた SharePoint サイトとファイルについて説明します。

- [SharePoint と OneDrive のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Teams のアイテム保持ポリシーでは、チャット メッセージとチャネル メッセージが保持されます。 チャット メッセージとチャネル メッセージは Exchange メールボックスに格納されますが、Exchange アイテム保持ポリシーの影響を受け取る必要があります。 Teams チャットおよび Teams チャネル メッセージに適用するアイテム保持ポリシーを設定する必要があります。 

ユーザー アカウントが削除された場合でも、ユーザー チャットは無期限に保持されます。 このデータを無期限に保持しない場合は、保持ポリシーを使用して、指定した時間後にユーザー チャットを削除するか、この削除をユーザー削除プロセスに含めるか検討してください。

- [Microsoft Teams のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Microsoft Teams のアイテム保持ポリシー](https://docs.microsoft.com/microsoftteams/retention-policies)

1 つのアイテム保持ポリシーを Microsoft 365 グループ、Teams チャット、Teams チャネル メッセージに適用できます。 

追加情報:

- [アイテム保持ポリシーの詳細を見る](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- Exchange[での保持タグと保持](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)ポリシー

## <a name="information-classification"></a>情報の分類

感度ラベルを使用すると、ゲスト アクセス、グループとチームのプライバシー、グループとチームの管理されていないデバイスによるアクセスを管理できます。 ラベルを適用すると、これらの設定はラベル設定で指定された通り自動的に構成されます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 は、指定した条件に基づいてファイルや電子メールに機密ラベルを自動適用する構成 (機密情報の種類の検出やトレーニング可能な分類子とのパターンマッチングなど) を構成できます。

- [秘密度ラベルをコンテンツに自動的に適用する](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

秘密度ラベルを使用してファイルを暗号化し、ファイルの暗号化を解除して読み取る権限を持つユーザーのみを許可できます。

- [秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [セキュリティの分離を使用してチームを構成する](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

追加情報:

- [秘密度ラベルの詳細](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>情報保護

DLP ポリシーを使用すると、SharePoint、Exchange、Teams 間で機密情報が偶発的に共有されるのを防ぐ可能性があります。 一連のルールに基づいて実行するアクション (アクセスのブロックなど) を指定するポリシーを作成できます。

- [データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

Teams の DLP は、機密情報を含むメッセージを削除することで、Teams チャットおよびチャネル メッセージの機密情報を保護するのに役立ちます。

- [データ損失防止と Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

プロジェクト コード名など、組織に固有の機密情報がある場合は、独自の機密情報の種類を作成して DLP ポリシーに適用して、グループ、チーム、および Sharepoint のコンテンツを保護できます。

- [カスタムの機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>ユーザーのセグメント化

情報の障壁を利用すると、データとユーザーをセグメント化して、グループ間の望ましくないコミュニケーションとコラボレーションを制限し、組織に対する利益相反を回避できます。 情報バリアを使用すると、組織内のユーザーグループ間でのファイルの共同作業、チャット、通話、会議の招待を許可または防止するポリシーを作成できます。

- [情報障壁](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Microsoft Teams の情報バリア](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [SharePoint で情報バリアを使用する](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[Exchange Online のセキュリティとコンプライアンス](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[情報を保護する](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
