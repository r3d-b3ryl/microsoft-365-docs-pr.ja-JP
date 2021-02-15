---
title: Microsoft 365 とセキュリティで保護された共同作業を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Teams でセキュリティで保護されたコンテンツのコラボレーションを設定して、データをその感度に基づいて保護する方法について学習します。
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233858"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Microsoft 365 とセキュリティで保護された共同作業を設定する

適切なユーザーと情報を簡単に共有できる一方で、過剰な共有を防ぐことが、組織の成功の鍵となります。 これには、機密データにアクセスする必要があるユーザーとのみ安全に共有できる機能が含まれます。 プロジェクトによっては、組織外のユーザーとの機密データの共有が含まれる場合があります。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

このコラボレーション ソリューション ガイダンスには、次の 2 つのコンポーネントが含まれています。
- 各プロジェクトの適切な保護レベルで Microsoft Teams を展開する
- プロジェクトごとに適切なセキュリティ設定を使用して外部共有を構成する

![適切な保護を使用して Teams を展開し、適切なセキュリティ設定を使用して外部共有を構成する](..\media\solutions-architecture-center\secure-collaboration-overview.png)

用途が広く使いやすいコンテンツ コラボレーション ツールが利用できない場合、ユーザーはドキュメントを電子メールで送信して共同作業を行う場合がよくがあります。 これは、グループ化を行うのに時間がかからない、間違いを起こしやすい方法であり、情報の不適切な共有のリスクを高める可能性があります。 情報の共有が難しすぎると感じ取った場合は、IT が管理していないコンシューマー製品の使用に戻る可能性があります。 これにより、さらに大きなリスクが生じ得る。

Microsoft 365 を使用すると、次に役立つさまざまな構成で Teams を展開できます。

- 知的財産を保護する
- 簡単な共同作業を可能にする
- セキュリティと操作性のバランスを取り、ユーザー満足度を高め、シャドウ IT のリスクを軽減する

ほとんどの組織には、さまざまな情報があります。情報が不適切に共有されている場合は、さまざまなレベルの感度とビジネスへの影響度が異なります。 特定の情報の感度に応じて、次の情報との共有を許可できます。

- だれでも (認証されていない)
- 組織内のユーザー
- 組織内の特定のユーザー
- 組織内外の特定のユーザー

マーケティング部門などの情報は、組織外で広く共有することを目的とします。 このメニューなどの情報は、外部共有を意図した情報ではなく、外部で共有されている場合はビジネスに影響を与える可能性はありません。 これらの種類の情報は、ほとんどまたは全く保護する必要はありません。

これらの同じマーケティング活動は、開発中ですが、組織内でのみ共有される場合があります。 この場合、Teams の既定の共有設定で十分な場合があります。

開発中の新しい製品に関する情報は、組織内でも機密性が高いと見なされる可能性があります。 この場合は、より高いレベルの保護が適切な場合があります。 たとえば、この情報へのアクセスを特定のチームのメンバーに制限できます。 プロジェクトによっては、ベンダーやパートナー組織など、組織外のユーザーとの共同作業が必要になる場合があります。

組織の成功に不可欠な情報や、厳しいセキュリティ要件やコンプライアンス要件を持つ情報には、さらに高いレベルの保護が必要になる場合があります。

![リスクスケールを低 (リリース済み) から高 (機密性の高いビジネス データ) に変更しました](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

上記のすべてのシナリオでは、Microsoft Teams のチームを使用して、情報の保存、共有、共同作業を行えます。 

セキュリティで保護されたコラボレーションを構成するには、次の Microsoft 365 の機能を使用します。

| 製品またはコンポーネント | 機能 | ライセンス |
|:-------|:-----|:-------|
| Microsoft Defender for Office 365 | SPO、OneDrive、Teams の安全な添付ファイル安全なドキュメントTeams の安全なリンク    | Microsoft 365 E1、E3、E5 |
| SharePoint    | サイトとファイル共有ポリシー, サイト共有のアクセス許可, リンクの共有, アクセス要求, サイトのゲスト共有の設定 | Microsoft 365 E1、E3、E5 |
| Microsoft Teams   | ゲスト アクセス、プライベート チーム、プライベート チャネル | Microsoft 365 E1、E3、E5 |
| Microsoft 365 コンプライアンス  | 秘密度ラベル    | Microsoft 365 E3、E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>あらゆる種類のデータに Teams を使用する

さまざまな機性を持つ情報へのアクセスを管理するために、Teams の 3 つの異なる [層の保護を開発しました](configure-teams-three-tiers-protection.md)。 これらの階層は、ニーズやビジネスに合わせてカスタマイズできます。 

![Teams の論理的なアーキテクチャ ポスターのサムネイル](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


ベースライン、機密、および機密性の高いこれらの層は、次の表に示すように、過剰な情報の漏えいや潜在的な情報漏洩を防ぐのに役立つ保護を徐々に強化します。 

|-|**ベースライン層**|**機密階層**|**機密性の高い階層**|
|:--|:-----------|:------------|:-------------------|
|パブリック チームまたはプライベート チーム|[Either/リンク/埋め込み]|プライベート|プライベート|
|認証されていない共有|Blocked|Blocked|Blocked|
|ファイル共有|可|可|共有できるのはチーム所有者のみです。|
|チーム メンバーシップ|誰でもパブリック チームに参加できます。<br>プライベート チームに参加するには、チーム所有者の承認が必要です。|参加するにはチーム所有者の承認が必要です。|参加するにはチーム所有者の承認が必要です。|
|ドキュメントの暗号化|||[Sensitivity label] (区別ラベル付き) で使用可能|
|ゲスト共有|可|許可またはブロック可能|許可またはブロック可能|
|非管理対象デバイス|制限なし|Web 専用アクセス|Blocked|

これらの層を構成するには、次の手順を実行します。

- ゲスト アクセスとプライベート チャネル用に Teams の設定を構成する
- 内部共有とゲスト共有、アクセス要求、および共有リンク用にチームに関連付けられた SharePoint サイトの設定を構成する
- 機密性の *高* い *層と機密性* の高い層の場合、チームを分類し、管理されていないデバイスからのゲスト共有とアクセスを制御する機密ラベルを構成する
- 機密性の *高い* 層の場合は、適用するドキュメントを暗号化する機密ラベルを構成する

ベースライン層から始めて、必要に応じて機密性の高い、機密性の高い層を使用するチームを追加して、組織内の情報を保護します。 開始するには、次のリソースを参照してください。

- [ベースライン保護を使用してチームを構成する](configure-teams-baseline-protection.md)
- [機密データに対する保護機能を使用してチームを構成する](configure-teams-sensitive-protection.md)
- [機密データに対する保護機能を使用してチームを構成する](configure-teams-highly-sensitive-protection.md)

組織内でも共有からの保護を強化する必要がある機密性の高いプロジェクトがある場合は、独自の機密ラベルを使用してファイルを暗号化するチームを構成して、チーム メンバーだけがファイルを読み取り可能にできます。 詳細 [については、「セキュリティ分離を使用してチームを構成する](secure-teams-security-isolation.md) 」を参照してください。

### <a name="sharing-with-people-outside-your-organization"></a>組織外のユーザーとの共有

組織外のユーザー [と任意の感度の情報を共有する必要がある場合があります](collaborate-with-people-outside-your-organization.md)。 これは、単一のドキュメントを 1 人のユーザーと共有したり、大規模なパートナー組織や世界中の人との主要なプロジェクトで共同作業を行う場合などです。 Microsoft 365 では、この範囲の外部共有は、機密情報の保護に役立つ適切な保護策を使用して、簡単に行うことができます。

次のリソースは、組織外のユーザーと共同作業するための環境のセットアップを開始するのに役立ちます。

- [ドキュメントで共同作業を行い](collaborate-on-documents.md) 、フォルダーの個々のファイルを共有します。
- [SharePoint サイトでゲスト](collaborate-in-site.md) と共同作業を行うサイトで共同作業を行います。
- [チーム内のゲストと](collaborate-as-team.md) 共同作業を行うチームとして共同作業を行います。

共有される情報の感度に応じて、過剰な共有を防ぐためのセーフガードを追加できます。 これらのリソースは、組織に必要な保護を設定するのに役立ちます。

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)
- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](share-limit-accidental-exposure.md)
- [セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md)

パートナー組織に主要なプロジェクトがある場合は、Azure Entitlement Management を使用して、プロジェクトに設定したチーム内の組織のゲストを管理できます。 詳細 [については、「管理されたゲストと B2B エクストラネットを作成する」](b2b-extranet.md) を参照してください。

## <a name="deploy-the-secure-collaboration-solution"></a>セキュリティで保護されたコラボレーション ソリューションを展開する

このソリューションを展開する準備ができたら、次の手順に進みます。
1. Teams の [3 つの異なる保護層を構成します](configure-teams-three-tiers-protection.md)。
2. 組織外の [ユーザーと任意の感度情報を共有する設定を構成します](collaborate-with-people-outside-your-organization.md)。

## <a name="see-also"></a>関連項目

[Microsoft 365 のセキュリティに関するドキュメント](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 コンプライアンスのドキュメント](https://docs.microsoft.com/microsoft-365/compliance)

[Microsoft Teams にようこそ](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
