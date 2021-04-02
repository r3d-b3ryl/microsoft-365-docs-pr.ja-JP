---
title: Microsoft Defender ATP でカスタム検出ルールを表示および管理する
ms.reviewer: ''
description: カスタム検出ルールを表示および管理する方法について説明します。
keywords: カスタム検出、表示、管理、アラート、編集、オンデマンドでの実行、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498753"
---
# <a name="view-and-manage-custom-detection-rules"></a>検出ルールの表示と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

既存のカスタム検出 [ルールを管理して](custom-detection-rules.md) 、脅威を効果的に検出し、アクションを実行します。 ルールの一覧を表示し、以前の実行を確認し、トリガーしたアラートを確認する方法について説明します。 必要に応じてルールを実行して変更できます。

## <a name="required-permissions"></a>必要なアクセス許可

カスタム検出を作成または管理するには、 [役割に](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) セキュリティ設定の管理権限 **が必要** です。

## <a name="view-existing-rules"></a>既存のルールの表示

既存のすべてのカスタム検出ルールを表示するには、[設定] [カスタム検出  >  **] に移動します**。 ページには、次の実行情報を含むすべてのルールが一覧表示されます。

- **Last run**—クエリの一致を確認し、アラートを生成するルールが最後に実行された場合
- **最終実行の状態**:ルールが正常に実行されたかどうか
- **次の実行**— 次のスケジュールされた実行
- **Status**—ルールが有効または無効になっているかどうか

## <a name="view-rule-details-modify-rule-and-run-rule"></a>ルールの詳細の表示、ルールの変更、およびルールの実行

カスタム検出ルールに関する包括的な情報を表示するには、[設定のカスタム検出] のルールの一覧からルールの **名前**  >  **を選択します**。 選択したルールに関するページには、次の情報が表示されます。

- アラート、実行状態、およびスコープの詳細を含む、ルールに関する一般的な情報
- トリガーされたアラートの一覧
- トリガーされたアクションの一覧

![カスタム検出ルール ページ](images/atp-custom-detection-rule-details.png)<br>
*カスタム検出ルール ページ*

また、このページからルールに対して次のアクションを実行することもできます。

- **Run**—ルールを直ちに実行します。 このアクションでは、次の実行の間隔もリセットされます。
- **Edit**—クエリを変更せずにルールを変更する
- **クエリの変更**—高度な検索でクエリを編集する
- **有効にする**  / **無効にする**-ルールを有効にするか、ルールの実行を停止する
- **Delete**—ルールをオフにし、削除する

>[!TIP]
>テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある [&#10003;] の選択列を使用します。

## <a name="related-topics"></a>関連項目
- [カスタム検出の概要](overview-custom-detections.md)
- [検出ルールの作成](custom-detection-rules.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [アラートの表示と整理](alerts-queue.md)
