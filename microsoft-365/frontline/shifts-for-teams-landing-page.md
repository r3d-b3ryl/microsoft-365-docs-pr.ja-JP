---
title: 現場担当者のシフト
description: スケジュール管理ツールである Shifts を Microsoft Teams で設定および管理するために必要な管理者ガイダンスを取得します。
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: microsoft-365-frontline
ms.collection:
- M365-collaboration
- m365-frontline
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-frontline
- m365solution-scenario
search.appverid: MET150
ms.localizationpriority: high
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: ce2c8da70b2fa6908518fc2f7d9489a2fdf578cd
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405730"
---
# <a name="shifts-for-frontline-workers"></a>現場担当者のシフト

Teams のスケジュール管理ツールであるシフトにより、現場の従業員が接続され、同期されます。高速で効果的なスケジュール管理と通信を実現するために、モバイルファーストが構築されています。 Shifts を使用すると、フロントライン マネージャーとワーカーはスケジュールをシームレスに管理し、連絡を取り合うことができます。

マネージャーは、チームのシフト スケジュールを作成、更新、管理できます。 シフトの割り当て、オープン シフトの追加、従業員からのスケジュール要求の承認を行うことができます。 従業員は、自分とチームのスケジュールを表示したり、可用性を設定したり、シフトを交換または提供したりするように要求したり、休暇を要求したり、出勤したりすることができます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

次のリソースを使用して、組織内の Shifts を設定および管理します。

## <a name="set-up-and-manage-shifts"></a>Shifts の設定と管理

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[シフトを管理する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)** 組織の Shifts を管理する方法の概要を説明します。 Shifts へのアクセスを制御する方法、Shift を Teams アプリ バーにピン留めして簡単にアクセスできるようにする方法、シフトベースのタグを有効にする方法などについて説明します。 |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[シフト管理のスケジュール所有者を管理する](schedule-owner-for-shift-management.md)** この機能を使用すると、従業員をチーム所有者にすることなく、チーム メンバーのアクセス許可をスケジュール所有者に昇格できます。         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Shifts データに関する FAQ](/microsoftteams/expand-teams-across-your-org/shifts/shifts-data-faq?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)** Shifts データの保存場所と、保持、取得、暗号化など、Shifts データに関連するその他のトピックについて説明します。        |

## <a name="shifts-connectors"></a>シフト コネクタ

スケジュール設定にサード パーティの従業員管理 (WFM) システムを使用している場合は、マネージド Shifts コネクタを介して Shifts と直接統合できます。 接続が設定されると、現場担当者は、Shifts 内から Blue Yonder WFMでスケジュールをシームレスに表示および管理できます。

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Shifts コネクタの概要](shifts-connectors.md)** Shifts コネクタとその動作の概要について説明します。 使用可能なマネージド コネクタと、サポートされている WFM システムについて説明します。   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[マネージド シフト コネクタ](shifts-connectors.md#managed-shifts-connectors)** パートナーと共同で開発されたマネージド シフト コネクタは、Microsoft またはパートナーによってホストおよび管理されます。 詳細については、 [Microsoft Teams の Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) および [Reflectionis Shifts コネクタの Microsoft Teams Shifts コネクタに関するページを参照してください](shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams)。    |
|   | **[Shifts コネクタ ウィザードを使用して、Microsoft 365 管理センターの Shifts コネクタ ウィザードWorkforce Management Blue Yonder に接続](shifts-connector-wizard.md)** すると、WFM システムへの接続をすばやく設定できます。 Blue Yonder 用の Microsoft Teams Shifts コネクタを使用して、Microsoft Teams の Shifts アプリを Blue Yonder 従業員管理 (Blue Yonder WFM) と統合します。
|  | **[PowerShell を使用して Shifts を Blue Yonder 従業員管理に接続する](shifts-connector-blue-yonder-powershell-setup.md)** PowerShell を使用して Blue Yonder の Teams Shifts コネクタを介してBlue Yonder 従業員管理への接続を設定する方法を学習します。         |
|   | **[PowerShell を使用して、Blue Yonder 従業員管理への Shifts 接続を管理する](shifts-connector-powershell-manage.md)** Shifts コネクタ ウィザードまたは PowerShell を使用してセットアップした後、PowerShell を使用して Blue Yonder 従業員管理への Shifts 接続を管理する方法に関するガイダンスを取得します。

## <a name="shifts-extensions"></a>拡張機能をシフトする

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Shifts Graph API を使用すると、Shifts データを外部 WFM システムと統合できます。 ユーザーに Teams の豊富なフロントエンド エクスペリエンスを提供しながら、バックエンドでカスタム Shifts エクスペリエンスを柔軟に構築できます。             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate を使用すると、Shift から情報を取得し、他のアプリでカスタム ワークフローを作成し、大規模な操作を実行できます。 コードをほとんどまたはまったく使用せずに、キー プロセスを自動化します。 トリガーとテンプレートは、マネージャーの承認が必要ない場合にシフト要求の自動承認を有効にするなど、さまざまなシナリオをサポートします。 |

## <a name="featured-training"></a>おすすめのトレーニング

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [ビデオ: Shifts とは](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [ビデオ: シフト スケジュールを作成する](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [ビデオ: シフト スケジュールを管理する](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
