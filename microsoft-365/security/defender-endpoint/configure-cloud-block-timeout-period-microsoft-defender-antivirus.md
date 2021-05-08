---
title: クラウド ブロックのMicrosoft Defender ウイルス対策期間を構成する
description: クラウドの決定を待機Microsoft Defender ウイルス対策ファイルの実行をブロックする期間を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、クラウド、タイムアウト、ブロック、期間、秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 02b8ee1c73116718d771847a43d6334e0723bd5c
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275311"
---
# <a name="configure-the-cloud-block-timeout-period"></a>クラウド ブロックのタイムアウト期間の構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

不審Microsoft Defender ウイルス対策検出すると、クラウド サービスのクエリ中にファイルが実行Microsoft Defender ウイルス対策[可能性があります](cloud-protection-microsoft-defender-antivirus.md)。

ファイルがブロックされる [既定の期間](configure-block-at-first-sight-microsoft-defender-antivirus.md) は 10 秒です。 ファイルの実行が許可される前に待機する追加の期間を指定できます。 これにより、クラウド サービスから適切な判断を受け取るのに十分な時間Microsoft Defender ウイルス対策できます。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>拡張クラウド ブロック タイムアウトを使用するための前提条件

[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) し、その前提条件を有効にしてから、延長タイムアウト期間を指定する必要があります。

## <a name="specify-the-extended-timeout-period"></a>延長タイムアウト期間を指定する

グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **mpEngine Windowsコンポーネント> Microsoft Defender ウイルス対策 >展開します。**

4. [拡張クラウド チェック **の構成] をダブルクリックし** 、オプションが有効になっているか確認します。 クラウドの決定を待っている間にファイルが実行されるのを防ぐための追加の時間を指定します。 1 秒から 50 秒の追加時間を秒で指定できます。 この時間は、既定の 10 秒に追加されます。

5. [**OK**] をクリックします。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策のWindows 10](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護を通じて次世代のウイルス対策テクノロジを使用する](cloud-protection-microsoft-defender-antivirus.md)
- [ブロックを一目で構成する](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)