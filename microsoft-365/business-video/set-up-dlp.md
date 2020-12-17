---
title: データの損失を防止する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: データ損失防止ポリシーの設定を管理する方法について説明します。
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702912"
---
# <a name="prevent-data-loss-with-dlp"></a>DLP を使用してデータ損失を防止する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

データ損失防止ポリシーは、社会保障番号や医療記録など、ビジネスの機密情報を特定して保護するのに役立ちます。 

## <a name="try-it"></a>演習

1. To get started, go to the [admin center,](https://admin.microsoft.com)and select **Setup**.
1. 下にスクロールして **データ損失防止の** 設定を行い、[表示] を選択し、[管理] を **選択します**。
1. ポリシーを編集するには、ポリシーを選択し、[ポリシーの編集] **を** 選択して、変更する内容を選択します。 たとえば、[場所] **を選択して** スキャンする項目を変更します。
1. Microsoft Teams のコンテンツのスキャンを有効にするには、トグル スイッチを **オン** の位置に切り替え、[保存] を選択 **します**。
1. ポリシー設定を編集するには、[編集] を **選択します**。
1. 検出された機密性の高いコンテンツの量と量が多いコンテンツに適用される個別のルールを設定する必要があります。 ボリュームの少ないルールを展開します。 Choose **Edit rule**.
1. 設定を確認し、必要に応じて調整します。 たとえば、電子メール テキストの **カスタマイズと** ポリシー ヒント テキストの **カスタマイズを選択できます**。 [**保存**] を選択します。
1. 高ボリューム ルールに対して繰り返します。 [保存 **] を** 選択し、[閉じる] **を選択します**。
1. 新しいポリシーを作成するには、[ポリシーの作成 **] を選択します**。
1. カスタム ポリシーを作成するか、テンプレートを使用して開始できます。 たとえば、HIPAA ポリシーを作成するには、[医療と健康] テンプレートを選択し、[米国の医療保険法 **(HIPAA)**] を選択します。 [**次へ**] を選択します。
1. ポリシーの名前と説明を入力します。 [**次へ**] を選択します。
1. スキャンする場所を選択します。 [**次へ**] を選択します。
1. 保護するコンテンツの種類を選択します。 [**次へ**] を選択します。
1. 機密情報が検出された場合の対応を選択します。 [**次へ**] を選択します。
1. アクセスをカスタマイズし、アクセス許可を上書きします。 [**次へ**] を選択します。
1. ポリシーを有効にするときに選択します。 [**次へ**] を選択します。
1. 設定を確認し、[作成] を **選択します**。 ポリシーが有効にされた後、記載された機密情報を含む電子メールがブロックされ、その情報を送信しようとした送信者に警告メッセージが表示されます。