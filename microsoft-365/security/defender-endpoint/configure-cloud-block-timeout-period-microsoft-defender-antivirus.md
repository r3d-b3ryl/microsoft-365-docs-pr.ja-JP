---
title: Microsoft Defender ウイルス対策クラウド ブロックのタイムアウト期間を構成する
description: Microsoft Defender Antivirus がクラウドの決定を待っている間にファイルの実行をブロックする時間を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、タイムアウト、ブロック、期間、秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691062"
---
# <a name="configure-the-cloud-block-timeout-period"></a>クラウド ブロックのタイムアウト期間を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策が疑わしいファイルを検出すると、Microsoft Defender ウイルス対策クラウド サービスのクエリ中にファイルが [実行されるのを防ぐ可能性があります](cloud-protection-microsoft-defender-antivirus.md)。

ファイルがブロックされる [既定の期間](configure-block-at-first-sight-microsoft-defender-antivirus.md) は 10 秒です。 ファイルの実行が許可される前に待機する追加の期間を指定できます。 これにより、Microsoft Defender ウイルス対策クラウド サービスから適切な判断を受け取るのに十分な時間が確保されます。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>拡張クラウド ブロック タイムアウトを使用するための前提条件

[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) し、その前提条件を有効にしてから、延長タイムアウト期間を指定する必要があります。

## <a name="specify-the-extended-timeout-period"></a>延長タイムアウト期間を指定する

グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを Microsoft Defender Antivirus > **MpEngine >展開する**

4. [拡張クラウド チェック **の構成] をダブルクリックし** 、オプションが有効になっているか確認します。 クラウドの決定を待っている間にファイルが実行されるのを防ぐための追加の時間を指定します。 1 秒から 50 秒の追加時間を秒で指定できます。 この時間は、既定の 10 秒に追加されます。

5. **[OK]** をクリックします。

## <a name="related-topics"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護を通じて次世代のウイルス対策テクノロジを使用する](cloud-protection-microsoft-defender-antivirus.md)
- [ブロックを一目で構成する](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)