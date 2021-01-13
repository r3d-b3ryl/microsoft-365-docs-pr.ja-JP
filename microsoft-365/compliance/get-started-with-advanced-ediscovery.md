---
title: Microsoft 365 で Advanced eDiscovery をセットアップする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: この記事では、ケースの作成と管理を開始できるよう Advanced eDiscovery をセットアップする方法について説明します。 また、必要な Microsoft サブスクリプションとライセンスについて説明します。 いくつかの簡単な手順を完了すると、Advanced eDiscovery ツールを使用する準備が整います。
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841178"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery のセットアップ

Microsoft 365 の Advanced [](overview-ediscovery-20.md#advanced-ediscovery-workflow) eDiscovery は、組織の内部および外部の調査に対応するデータを保持、収集、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 Advanced eDiscovery を展開するために必要なタスクは何もありませんが、組織で Advanced eDiscovery ケースの作成と使用を開始して調査を管理するには、IT 管理者と電子情報開示マネージャーが完了する必要があるいくつかの前提条件タスクがあります。

この記事では、Advanced eDiscovery をセットアップするために必要な手順について説明します。 これには、Advanced eDiscovery にアクセスしてケースにカストディアンを追加するために必要な適切なライセンスを確保し、法務チームと調査チームにアクセス許可を割り当て、ケースにアクセスして管理できる権限が含まれます。

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>手順 1: 適切なライセンスを確認して割り当てる

Advanced eDiscovery のライセンスには、適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。

- **組織のサブスクリプション:** Microsoft 365 コンプライアンス センターまたはセキュリティ & コンプライアンス センターで Advanced eDiscovery にアクセスするには、組織に次のいずれかを設定する必要があります。

  - Microsoft 365 E5 または Office 365 E5 サブスクリプション
  
  - E5 コンプライアンス アドオンが含まれている Microsoft 365 E3 サブスクリプション

  - E5 電子情報開示および監査アドオンを使用した Microsoft 365 E3 サブスクリプション

  既存の Microsoft 365 E5 プランをお持ちで、Advanced eDiscovery を試す場合は、既存のサブスクリプションに[Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)を追加するか、Microsoft 365 E5 の試用版にサインアップできます。 [](https://www.microsoft.com/microsoft-365/enterprise)

- **ユーザーごとのライセンス:** Advance eDiscovery ケースでユーザーを保管担当者として追加するには、組織のサブスクリプションに応じて、そのユーザーに次のいずれかのライセンスが割り当てられている必要があります。

  - Microsoft 365: ユーザーには、Microsoft 365 E5 ライセンス、E5 コンプライアンス アドオン ライセンス、または E5 電子情報開示および監査アドオン ライセンスが割り当てられている必要があります。

  - Office 365: ユーザーには 365 E5 ライセンスOffice割り当てられている必要があります。

   ライセンスを割り当てる方法については、「ライセンスをユーザーに割り当てる [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> Advanced eDiscovery ケースに保管担当者として追加する必要があるのは、E5 ライセンス (または適切なアドオン ライセンス) のみです。 Advanced eDiscovery を使用してケースを管理し、ケース データをレビューする IT 管理者、電子情報開示管理者、弁護士、パラリーガル、または調査担当者は、E5 またはアドオン ライセンスを必要とします。

## <a name="step-2-assign-ediscovery-permissions"></a>手順 2: 電子情報開示のアクセス許可を割り当てる

Advanced eDiscovery にアクセスしたり、Advanced eDiscovery ケースのメンバーとして追加したりするには、ユーザーに適切なアクセス許可を割り当てる必要があります。 具体的には、セキュリティ/コンプライアンス センターで電子情報開示マネージャー役割グループのメンバーとしてユーザー&必要があります。 この役割グループのメンバーは、Advanced eDiscovery ケースを作成および管理できます。 メンバーの追加と削除、保管担当者とコンテンツの場所の保留、法的情報保留通知の管理、ケースに関連付けられた検索の作成と編集、レビュー セットへの検索結果の追加、レビュー セット内のデータの分析、Advanced eDiscovery ケースからのエクスポートとダウンロードを実行できます。

電子情報開示マネージャー役割グループにユーザーを追加するには、次の手順を実行します。

1. Microsoft 365 組織の管理者アカウントの資格情報を使用して、 [https://protection.office.com/permissions](https://protection.office.com/permissions) アクセスしてサインインします。

2. [アクセス **許可] ページ** で、 **電子情報開示マネージャーの役割グループを** 選択します。

3. [電子情報開示マネージャー] フライアウト ページで、[電子 **情報開示マネージャー]** セクションの横にある [編集 **] をクリック** します。

4. 役割グループ **の編集ウィザードの [電子情報開示マネージャー** の選択] ページで、[電子情報開示マネージャーの選択 **] をクリックします**。

5. [ **追加]** をクリックし、役割グループに追加するすべてのユーザーのチェック ボックスをオンにします。

6. [ **追加]** をクリックして選択したユーザーを追加し、[完了] を **クリックします**。

7. [**保存]** をクリックしてユーザーを役割グループに追加し、[閉じる] をクリックして手順を完了します。

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>電子情報開示マネージャー役割グループの詳細

電子情報開示マネージャー役割グループには 2 つのサブグループがあります。 これらのサブグループの違いは、スコープに基づきます。

- **電子情報開示マネージャー:** 作成した、またはメンバーである Advanced eDiscovery ケースを表示および管理できます。 別の電子情報開示マネージャーがケースを作成しても、そのケースのメンバーとして 2 番目の電子情報開示マネージャーを追加しない場合、2 番目の電子情報開示マネージャーはコンプライアンス センターの [Advanced eDiscovery] ページでケースを表示または開くこがれません。 一般に、組織内のほとんどのユーザーを電子情報開示マネージャーサブグループに追加できます。

- **電子情報開示管理者:** 電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。 さらに、電子情報開示管理者は、次のことができます。

  - [Advanced eDiscovery] ページにリストされたすべてのケースを表示します。
  
  - 自分自身をケースのメンバーとして追加した後、組織のすべてのケースを管理します。

  - 組織内のすべてのケースのケース データにアクセスしてエクスポートします。

  アクセス範囲が広いため、電子情報開示管理者のサブグループのメンバーになっている管理者は少数です。

電子情報開示のアクセス許可の詳細と、電子情報開示マネージャーの役割グループに割り当てられている各役割の説明については、「電子情報開示のアクセス許可を割り当てる」を [参照してください](assign-ediscovery-permissions.md)。

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>手順 3: Advanced eDiscovery のグローバル設定を構成する

組織内のユーザーがケースの作成と使用を開始する前に完了する最後の手順は、組織内のすべてのケースに適用されるグローバル設定を構成する手順です。 現時点では、唯一のグローバル設定は弁護士/ *依頼* 人特権の検出です (今後、より多くのグローバル設定が利用可能になります)。 この設定により、レビュー セット内のデータを分析するときに、弁護士/依頼人特権モデルを実行できます。 このモデルでは、機械学習を使用して、ドキュメントに実際に合法的なコンテンツが含まれている可能性を判断します。 また、ドキュメントの参加者と弁護士リスト (モデルのセットアップ時に提出するリスト) を比較して、ドキュメントに弁護士の参加者が少なくとも 1 人いないかどうかを判断します。

弁護士/依頼人特権検出モデルの設定と使用の詳細については [、「Advanced eDiscovery](attorney-privilege-detection.md)で弁護士/依頼人特権の検出をセットアップする」を参照してください。

> [!NOTE]
> これは、いつでも実行できるオプションの手順です。 弁護士/依頼人特権の検出モデルを実装しない場合でも、Advanced eDiscovery ケースの作成と使用を妨げるものではありません。

## <a name="next-steps"></a>次の手順

Advanced eDiscovery をセットアップした後、ケースを [作成する準備が整いました](create-and-manage-advanced-ediscoveryv2-case.md)。
