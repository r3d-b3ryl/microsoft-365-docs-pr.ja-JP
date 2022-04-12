---
title: Microsoft Defender ウイルス対策 インターフェイスを非表示にする
description: Windows セキュリティ アプリでは、ウイルスと脅威の保護タイルを非表示にすることができます。
keywords: UI ロックダウン、ヘッドレス モード、アプリの非表示、設定の非表示、インターフェイスの非表示
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: fdd212efd50d55bbcdae80275f5d2ca8a97cdeb3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787668"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>ユーザーがMicrosoft Defender ウイルス対策ユーザー インターフェイスを表示または操作できないようにする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

グループ ポリシーを使用すると、エンドポイント上のユーザーがMicrosoft Defender ウイルス対策 インターフェイスを表示できないようにすることができます。 また、スキャンを一時停止しないようにすることもできます。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Microsoft Defender ウイルス対策 インターフェイスを非表示にする

Windows 10バージョン 1703 では、インターフェイスを非表示にすると、Microsoft Defender ウイルス対策通知が非表示になり、ウイルス&脅威保護タイルがWindows セキュリティ アプリに表示されなくなります。

設定が **[有効]** に設定されている場合:

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="シールド アイコンとウイルスと脅威の保護セクションのないWindows セキュリティ" lightbox="../../media/wdav-headless-mode-off-1703.png":::

設定が **[無効]** または [未構成] に設定されている場合:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="シールド アイコンと脅威保護セクションを含むWindows セキュリティ" lightbox="../../media/wdav-headless-mode-1703.png":::

> [!NOTE]
> インターフェイスを非表示にすると、Microsoft Defender ウイルス対策通知がエンドポイントに表示されなくなります。 Microsoft Defender for Endpoint通知は引き続き表示されます。 [エンドポイントに表示される通知を個別に構成](configure-notifications-microsoft-defender-antivirus.md)することもできます。

以前のバージョンのWindows 10では、この設定はWindows Defenderクライアント インターフェイスを非表示にします。 ユーザーが開こうとすると、"システム管理者がこのアプリへのアクセスを制限しました" という警告が表示されます。

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="1703 より前のバージョンのWindows 10でヘッドレス モードが有効になっている場合の警告メッセージ" lightbox="../../media/wdav-headless-mode-1607.png":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>グループ ポリシーを使用して、Microsoft Defender AV インターフェイスをユーザーから非表示にする

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. ツリーを展開して、**クライアント インターフェイス> Microsoft Defender ウイルス対策 >コンポーネントをWindowsします**。

5. **[ヘッドレス UI モードを有効にする]** 設定をダブルクリックし、オプションを **[有効]** に設定します。 **[OK]** をクリックします。

ユーザーが PC で保護をフォーム変更できないようにする方法の詳細については、「ユーザー [がポリシー設定をローカル](configure-local-policy-overrides-microsoft-defender-antivirus.md) で変更できないようにする」を参照してください。

## <a name="prevent-users-from-pausing-a-scan"></a>ユーザーがスキャンを一時停止できないようにする

ユーザーがスキャンを一時停止できないようにすることができます。これは、スケジュールされたスキャンまたはオンデマンド スキャンがユーザーによって中断されないようにするのに役立ちます。

> [!NOTE]
> この設定は、Windows 10ではサポートされていません。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>グループ ポリシーを使用して、ユーザーがスキャンを一時停止できないようにする

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. ツリーを展開して、**スキャン****Microsoft Defender ウイルス対策コンポーネント** \> **をWindows**\>します。

5. [ **ユーザーによるスキャンの一時停止を許可** する] 設定をダブルクリックし、オプションを **[無効]** に設定します。 **[OK]** をクリックします。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策を使用してエンド ユーザー操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
