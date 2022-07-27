---
title: シフト コネクタ
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Shifts コネクタと、それらを使用して Shifts を従業員管理システムに接続する方法について説明します。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: c211e066a1b5c6ad610c2f3be703d50be3ecf6af
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994873"
---
# <a name="shifts-connectors"></a>シフト コネクタ

## <a name="overview"></a>概要

Shifts コネクタを使用すると、Microsoft Teams のスケジュール管理ツールである Shifts と、従業員管理 (WFM) システムを統合できます。 接続が設定されると、現場担当者は、Shifts 内から Blue Yonder WFM でスケジュールをシームレスに表示および管理できます。

WFM システムを Teams に接続すると、現場の従業員はスケジュールをより効果的に管理し、より高いエンゲージメントと生産性を実現するために日常のプロセスを合理化できます。 現場担当者は、スケジュール設定、コミュニケーション、コラボレーションを行うための 1 つの場所を持ち、どこからでも、あらゆるデバイスで作業を完了する必要があります。

この記事では、Shifts コネクタとその動作の概要について説明します。

## <a name="how-shifts-connectors-work"></a>Shifts コネクタのしくみ

コネクタは、WFM システムとシフトの間でスケジュール データを同期し、組織のスケジュールを Teams に取り込みます。 シフトは、現場担当者がスケジュールのニーズに応じて取り組む場所です。 WFM システムは、ビジネス ルール、コンプライアンス、インテリジェンスの記録システムです。

コネクタを介したデータ フローは、両方の方法でスケジュールが常に最新であることを確認します。 WFM システムのスケジュールは Shifts に同期されます。 また、Shifts でスケジュールに加えられた変更は、WFM システムにリアルタイムで同期されます。 レコードのシステムとして、データが Shifts に保存される前に、WFM システムによってすべてのビジネス ルールが適用されます。

## <a name="managed-shifts-connectors"></a>管理対象シフト コネクタ

管理対象シフト コネクタは、パートナーと共同で開発されたコネクタです。 管理対象コネクタは、Microsoft またはパートナーによってホストおよび管理されます。 管理対象コネクタでは、最小限のセットアップのみが必要です。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Blue Yonder 用 Microsoft Teams Shifts コネクタ
<a name="blue_yonder"> </a>

Blue Yonder 用 Teams Shifts コネクタは、Microsoft がホストおよび管理するファースト パーティ製品です。 このコネクタを使用すると、Shifts と Blue Yonder 従業員管理 (Blue Yonder WFM) バージョン 2020.3、2021.1、または 2021.2 を統合してスケジュールを管理し、最新の状態に保つことができます。  

> [!NOTE]
> Blue Yonder WFM バージョン 2020.3 または 2021.1 の場合は、2020.3.0.4 または 2021.1.0.3 パッチを適用してください。 この修正プログラムは、ユーザーが Shifts で永続的なエラー メッセージを受け取る問題を修正します。 また、ユーザーが Shifts でを空き時間状況を更新できない問題も修正されます。

:::image type="content" source="media/shifts-connector-blue-yonder.png" alt-text="モバイル デバイスの Shifts でのスワップ要求、デスクトップ上の Teams での承認の要求、Blue Yonder WFM のスケジュールを示すスクリーンショット。" lightbox="media/shifts-connector-blue-yonder.png":::

フロントライン マネージャーは次のことができます。

- Blue Yonder WFM でシフトとスケジュールを公開し、Shifts で表示します。
- Blue Yonder WFM で開いているシフトを作成、管理、割り当て、Shifts で表示します。
- Blue Yonder WFM で作成されたオープン シフトを Shifts で割り当てます。
- Blue Yonder WFM で休暇を作成、編集、削除し、Shifts で表示します。
- Blue Yonder WFMと Shifts の両方のワーカーからのスケジュール要求を表示および承認します。
- Blue Yonder WFM でワーカーの可用性を設定および更新し、Shifts で表示します。

現場担当者は次のことができます。

- Shifts で、自分とチームのシフトとスケジュールを確認すること。
- Shifts で、オフ、オープン シフト、スワップ シフトを要求すること。
- Shifts で可用性を設定すること。

現在、以下はサポートされていません。

- Shifts でシフトを追加、編集、削除、保存、発行すること。
- Shifts で休暇を追加、編集、削除、保存、公開すること。
- Shifts で開いているシフトを追加、編集、削除、保存、公開すること。

フロントライン マネージャーまたはワーカーが Shifts でこれらのアクションのいずれかを実行しようとすると、アクションがサポートされていないことを知らせるメッセージが表示されます。

#### <a name="example-scenario"></a>シナリオ例

マネージャーである Eden は、コネクタを介して Teams の Shifts に同期される Blue Yonder WFM でスケジュールを公開します。 スタッフメンバーである Alex は、モバイル デバイス上の Teams で通知を受け取り、スケジュールと割り当てられたシフトを表示します。

Alex は少し時間を取る必要があり、Shifts を使用して 1 日の休暇を要求します。 要求は、コネクタを介してリアルタイムで Blue Yonder WFM に送信されます。 Blue Yonder WFM は、要求がビジネス ルールに準拠し、要求が作成されるようにします。 Blue Yonder WFM の要求が表示され、承認され、承認が Teams に同期されます。 (Eden は、Shifts で要求を表示および承認することもできます)。 Alex は Teams で要求が承認されたことを通知され、更新されたスケジュールが表示されます。

Alex は、シフトを同僚と入れ替えたいと考えています。 Shifts では、Alex は Blue Yonder WFM のビジネス ルールに基づいてスワップの対象となるすべてのシフトの一覧を表示します。 Alex は、現在 Gena に割り当てられているシフトを選択します。 Gena は、モバイル デバイス上の Teams で通知を受け取り、スワップ要求を受け入れます。 Eden は Shifts で要求を確認して承認し、承認は Blue Yonder WFM に同期されます。 (Blue Yonder WFM で要求を確認して承認することもできます)。 Alex と Gena は Teams で通知を受け取り、更新されたスケジュールを表示します。

#### <a name="set-up-a-connection"></a>接続を設定する

コネクタを使用して Shifts と Blue Yonder WFM を統合するには、いくつかの手順を実行します。 Microsoft 365 管理センターの Shifts コネクタ ウィザードを使用して、接続をすばやく設定できます。 ウィザードは、選択した設定に基づいてコネクタを構成し、接続を作成します。 PowerShell を使用する場合は、接続に使用できる PowerShell スクリプトも用意されています。

詳細なガイダンスについては、「Windows への PowerShell のインストール」を参照してください。

- [Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder 従業員管理に接続する](shifts-connector-wizard.md)
- [PowerShell を使用して Shifts を Blue Yonder Workforce Management に接続する](shifts-connector-blue-yonder-powershell-setup.md)

接続が設定されたら、PowerShell を使用して、必要に応じていつでも接続設定を更新および変更できます。 コネクタ自体については、アップグレードやメンテナンスについて心配する必要はありません。 その処理を行います。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Microsoft Teams 用の Reflectionis Shifts コネクタ

Microsoft Teams 用の Reflectionis Shifts コネクタは、Zebra によってホストおよび管理されています。 このコネクタを使用すると、Shifts と Reflectionis WFM システムを統合してスケジュールを管理し、それらを最新の状態に保つことができます。

現場担当者は Teams の Shifts でスケジュールにアクセスでき、その要求は Shifts から Reflectionis Workforce Scheduler (RWS) に同期されます。 RWS で作成された要求とシフトの状態は、Teams の Shifts と同期されます。

:::image type="content" source="media/shifts-connector-reflexis.png" alt-text="モバイル デバイスのシフトの一覧と、Reflectionis のスケジュールを示すスクリーンショット。" lightbox="media/shifts-connector-reflexis.png":::

フロントライン マネージャーは次のことができます。

- Shifts でシフトとスケジュールを公開し、Shifts で表示します。
- Reflectionis と Shifts の両方でシフトを編集します。
- Reflectionis と Shifts の両方でオープン シフトを作成、管理、割り当てます。
- Reflectionis と Shifts の両方のワーカーからのスケジュール要求を表示および承認します。

現場担当者は次のことができます。

- Shifts で、自分とチームのシフトとスケジュールを確認すること。
- Shifts で、休暇の要求、シフトのオープン、シフトのスワップとオファーを行います。

詳細は、https://connect.zebra.com/microsoft-connectors を参照してください。

## <a name="related-articles"></a>関連記事

- [Teams で組織の シフト アプリを管理する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
