---
title: Microsoft Defender ウイルス対策クラウド ブロックのタイムアウト期間を構成する
description: クラウドの決定を待機している間、Microsoft Defender ウイルス対策がファイルの実行をブロックする時間を構成できます。
keywords: Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, cloud, timeout, block, period, seconds
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
ms.openlocfilehash: 0ad46ff70ed2542ebed423a02eba6cc0810a99ca
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418764"
---
# <a name="configure-the-cloud-block-timeout-period"></a>クラウド ブロックのタイムアウト期間の構成

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策が疑わしいファイルを見つけると、[Microsoft Defender ウイルス対策 クラウド サービス](cloud-protection-microsoft-defender-antivirus.md)に対するクエリ中にファイルが実行されるのを防ぐことができます。

ファイルが [ブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) される既定の期間は 10 秒です。 セキュリティ管理者の場合は、ファイルの実行が許可されるまでの待機時間を長く指定できます。 クラウド ブロックのタイムアウト期間を延長すると、Microsoft Defender ウイルス対策 クラウド サービスから適切な決定を受け取るのに十分な時間があることを確認するのに役立ちます。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>拡張クラウド ブロック タイムアウトを使用するための前提条件

延長タイムアウト期間を指定する前に、[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)とその前提条件を有効にする必要があります。

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーを使用して延長タイムアウト期間を指定する

[Microsoft エンドポイント マネージャーのエンドポイント セキュリティ ポリシー](/mem/intune/protect/endpoint-security-policy)を使用して、クラウド ブロックのタイムアウト期間を指定できます。

1. エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) に移動し、サインインします。

2. **[エンドポイント セキュリティ**] を選択し、[**管理**] で [**ウイルス対策**] を選択します。

3. ウイルス対策ポリシーを選択 (または作成) します。

4. [ **構成設定]** セクションで、[ **クラウド保護**] を展開します。 次に、**Microsoft Defender ウイルス対策 [延長タイムアウト (秒**)] ボックスで、1 秒から 50 秒までの時間を秒単位で指定します。 指定したものは、既定の 10 秒に追加されます。

5. (この手順は省略可能です)ウイルス対策ポリシーに他の変更を加えます。 (ヘルプが必要ですか? [Microsoft IntuneのMicrosoft Defender ウイルス対策 ポリシーの設定](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)を参照してください)。

6. **[次へ**] を選択し、ポリシーの構成を完了します。

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>グループ ポリシーを使用して延長タイムアウト期間を指定する

グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます

2. 構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

3. **グループ ポリシー管理エディター** で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを展開して **、MpEngine** **Microsoft Defender ウイルス対策コンポーネント** \> **をWindows**\>します。

4. [ **拡張クラウドの構成] チェック** をダブルクリックし、オプションが有効になっていることを確認します。 

   クラウドの決定を待機している間にファイルが実行されないようにする余分な時間を指定します。 1 秒から 50 秒までの余分な時間を秒単位で指定します。 指定したものは、既定の 10 秒に追加されます。

5. **[OK]** を選択します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md) 
