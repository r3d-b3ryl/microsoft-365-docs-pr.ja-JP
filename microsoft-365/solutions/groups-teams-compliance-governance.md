---
title: Microsoft 365 グループ、チーム、および SharePoint コラボレーションのコンプライアンスオプション
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
description: Microsoft 365 グループ、チーム、および SharePoint コラボレーションのコンプライアンスオプションについて説明します。
ms.openlocfilehash: e1ca6e638b2d44ae3b04e2a0f13222424e89714d
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613632"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 グループ、チーム、および SharePoint コラボレーションのコンプライアンスオプション

Microsoft 365 は、ユーザーが共同作業する際にコンプライアンスを維持するための包括的なツールを提供しています。 これらのオプションを確認し、ビジネスニーズへの対応方法、データの機密性、およびユーザーが共同作業する必要のあるユーザーの範囲を検討してください。

次の表に、Microsoft 365 で利用できるコンプライアンスコントロールのクイックリファレンスを示します。 詳細については、以下のセクションを参照してください。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|情報の保存|||
||グループのメールと SharePoint のコンテンツを保持する|[SharePoint と OneDrive のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||チャットおよびメッセージの保持|[Microsoft Teams のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|情報の分類|||
||グループとチームを分類する|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||機密コンテンツを自動的に分類する|[機密ラベルをコンテンツに自動的に適用する](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||機密コンテンツを暗号化する|[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|情報保護|||
||機密情報の損失を防止する|[データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||チャットの機密情報を保護します。|[データ損失防止と Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||組織の機密情報を定義する|[カスタムの機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|ユーザーのセグメント化|||
||ユーザーセグメント間の通信を制限する|[情報障壁](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>情報の保存

アイテム保持ポリシーは、ファイル、メッセージ、メールを含むグループと teams のコラボレーションに使用するアイテムを保持または削除するために使用できます。 ポリシーは、保持および削除、または保持のみ、または削除のいずれかに設定できます。 アイテム保持ポリシーの対象となる情報は、グループまたはチームの有効期限が切れた場合や削除された場合に保護されます。

Microsoft 365 グループのアイテム保持ポリシーを構成すると、グループメールボックスと関連付けられた SharePoint サイトとファイルがカバーされます。

- [SharePoint と OneDrive のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Teams のアイテム保持ポリシーには、チャットおよびチャネルメッセージが保持されます。 チャットおよびチャネルメッセージは Exchange メールボックスに格納されますが、Exchange のアイテム保持ポリシーの影響を受けません。 Teams チャットおよび Teams チャネルメッセージに適用するアイテム保持ポリシーを設定する必要があります。

- [Microsoft Teams のアイテム保持ポリシーの詳細](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Microsoft Teams の保持ポリシー](https://docs.microsoft.com/microsoftteams/retention-policies)

1つのアイテム保持ポリシーを設定して、Microsoft 365 グループ、Teams チャット、Teams チャネルメッセージに適用することができます。 

追加情報:

- [アイテム保持ポリシーの詳細を見る](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- Exchange の[保持タグとアイテム保持ポリシー](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="information-classification"></a>情報の分類

機密ラベルを使用すると、ゲストアクセス、グループおよびチームのプライバシー、および管理されていないデバイスによるグループと teams へのアクセスを管理できます。 ラベルを適用することで、これらの設定はラベル設定によって指定されたとおりに自動的に構成されます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Trainable 分類子との機密情報の種類やパターンマッチングを含む、指定した条件に基づいて、ファイルや電子メールに機密ラベルを自動的に適用するように Microsoft 365 を構成できます。

- [機密ラベルをコンテンツに自動的に適用する](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

機密ラベルを使用してファイルを暗号化すると、アクセス許可を持つユーザーだけがファイルを復号化して読み取ることができるようになります。

- [秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [セキュリティの分離を使用してチームを構成する](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

追加情報:

- [秘密度ラベルの詳細](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>情報保護

DLP ポリシーによって、SharePoint、Exchange、および Teams 間で機密情報を誤って共有することを防ぐことができます。 ルールのセットに基づいて実行するアクション (ブロックアクセスなど) を指定するポリシーを作成できます。

- [データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

Teams の DLP は、機密情報を含むメッセージを削除することで、Teams のチャットおよびチャネルメッセージ内の機密情報を保護するのに役立ちます。

- [データ損失防止と Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

組織に固有の機密情報 (プロジェクトコード名など) がある場合は、独自の機密情報の種類を作成し、それらを DLP ポリシーに適用して、グループ、teams、および Sharepoint のコンテンツを保護することができます。

- [カスタムの機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>ユーザーのセグメント化

情報の障壁により、データとユーザーをセグメント化して、グループ間の不要な通信や共同作業を制限したり、組織内での競合を回避したりすることができます。 情報バリアを使用すると、組織内のユーザーグループ間でのファイルコラボレーション、チャット、通話、または会議への招待を許可または禁止するポリシーを作成できます。

- [情報障壁](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Microsoft Teams の情報障壁](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [SharePoint で情報バリアを使用する](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>関連項目

[コラボレーションガバナンスの計画のステップバイステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーションのガバナンス計画を作成する](collaboration-governance-first.md)

[Exchange Online のセキュリティとコンプライアンス](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[情報を保護する](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
