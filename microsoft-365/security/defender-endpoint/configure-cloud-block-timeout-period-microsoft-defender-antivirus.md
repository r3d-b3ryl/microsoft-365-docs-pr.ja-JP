---
title: クラウド ブロックのMicrosoft Defender ウイルス対策期間を構成する
description: クラウドの決定を待機Microsoft Defender ウイルス対策ファイルの実行をブロックする期間を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、クラウド、タイムアウト、ブロック、期間、秒
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
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: e3f267218155b7aa503237aaa4e52e2e8637019d
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110801"
---
# <a name="configure-the-cloud-block-timeout-period"></a>クラウド ブロックのタイムアウト期間の構成

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

不審Microsoft Defender ウイルス対策検出すると、クラウド サービスのクエリ中にファイルが実行Microsoft Defender ウイルス対策[可能性があります](cloud-protection-microsoft-defender-antivirus.md)。

ファイルがブロックされる [既定の期間](configure-block-at-first-sight-microsoft-defender-antivirus.md) は 10 秒です。 セキュリティ管理者の場合は、ファイルの実行が許可される前に待機する時間を長く指定できます。 クラウド ブロックのタイムアウト期間を延長すると、クラウド サービスから適切な判断を受け取るのに十分な時間Microsoft Defender ウイルス対策できます。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>拡張クラウド ブロック タイムアウトを使用するための前提条件

[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) し、その前提条件を有効にしてから、延長タイムアウト期間を指定する必要があります。

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>データを使用して延長タイムアウト期間をMicrosoft エンドポイント マネージャー

クラウド ブロックのタイムアウト期間は、エンドポイント セキュリティ ポリシーを使用して指定[Microsoft エンドポイント マネージャー。](/mem/intune/protect/endpoint-security-policy)

1. 管理センター ( ) エンドポイント マネージャーに移動し [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) 、サインインします。

2. [エンドポイント **セキュリティ] を** 選択し、[管理] で **[ウイルス** 対策] を **選択します**。

3. ウイルス対策ポリシーを選択 (または作成) します。

4. [構成設定 **] セクションで** 、[クラウド保護] **を展開します**。 次に、[Microsoft Defender ウイルス対策延長タイムアウト (秒) ボックスで、1 秒から 50 秒の時間を秒単位で指定します。 指定した値は、既定の 10 秒に追加されます。

5. (この手順は省略可能です)ウイルス対策ポリシーに他の変更を加えます。 (ヘルプが必要ですか? [「設定ポリシー Microsoft Defender ウイルス対策」を参照Microsoft Intune.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)

6. [ **次へ]** を選択し、ポリシーの構成を完了します。

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>グループ ポリシーを使用して延長タイムアウト期間を指定する

グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。

1. グループ ポリシー管理コンピューターで、グループ ポリシー管理 [コンソールを開きます。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[** コンピューターの構成] **に** 移動し、[管理用テンプレート] **を選択します**。

3. MpEngine のコンポーネント **Windowsツリー** \> **Microsoft Defender ウイルス対策** \> **展開します**。

4. [拡張クラウド チェック **の構成] をダブルクリックし** 、オプションが有効になっているか確認します。 

   クラウドの決定を待っている間にファイルが実行されるのを防ぐための余分な時間を指定します。 1 秒から 50 秒の余分な時間を秒で指定します。 指定した値は、既定の 10 秒に追加されます。

5. **[OK]** を選択します。

 
