---
title: Microsoft Defender ウイルス対策によってモバイル デバイスを更新する方法を定義する
description: ラップトップなどのモバイル デバイスをMicrosoft Defender ウイルス対策保護更新プログラムで更新する方法を管理します。
keywords: 更新プログラム, 保護, 更新のスケジュール, バッテリ, モバイル デバイス, ノート PC, ノートブック, オプトイン, Microsoft update, wsus, override
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: e7f8327dc4bae972528943eceb8cf5c6f28fb0c4
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416356"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

モバイル デバイスと VM では、パフォーマンスが更新プログラムの影響を受けないように、より多くの構成が必要になる場合があります。

これらのデバイスに役立つ 2 つの設定があります。

- WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする
- バッテリ電源で実行しているときにセキュリティ インテリジェンスの更新を防止する

次の記事は、このような状況でも役立つ場合があります。
- [スケジュールされたスキャンとキャッチアップ スキャンの構成](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする

Microsoft Update を使用すると、モバイル デバイスのセキュリティ インテリジェンスが企業ネットワークに接続されていない場合や WSUS 接続がない場合に、Microsoft Defender ウイルス対策実行されているセキュリティ インテリジェンスを最新の状態に保つことができます。

つまり、MICROSOFT Update をオーバーライドするように WSUS を設定した場合でも、(Microsoft Update 経由で) 保護更新プログラムをデバイスに配信できます。

モバイル デバイスで Microsoft Update にオプトインするには、次のいずれかの方法を使用します。

- グループ ポリシーを使用して設定を変更します。
- VBScript を使用してスクリプトを作成し、ネットワーク内の各コンピューターで実行します。
- **設定** メニューを使用して、ネットワーク上のすべてのコンピューターを手動でオプトインします。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>グループ ポリシーを使用して Microsoft Update にオプトインする

1. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **ポリシー** ]、[ **管理用テンプレート]** の順に選択します。

4. ツリーを展開して、**シグネチャ更新** プログラムMicrosoft Defender ウイルス対策 **コンポーネント** \> **をWindows**\>します。

5. **[Microsoft Update からのセキュリティ インテリジェンス更新プログラムの許可****] を [有効]** に設定し、[OK] を選択 **します**。

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>VBScript を使用して Microsoft Update にオプトインする

1. VBScript を作成するには、MSDN の記事 [「Microsoft Update へのオプトイン](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 」の手順に従います。

2. 作成した VBScript をネットワーク内の各コンピューターで実行します。

### <a name="manually-opt-in-to-microsoft-update"></a>Microsoft Update に手動でオプトインする

1. オプトインする **コンピューターのセキュリティ** 設定 **&更新プログラム** でWindows Updateを開きます。

2. [ **詳細設定] オプションを** 選択します。

3. [Windows **更新時に他の Microsoft 製品の更新プログラムを提供** する] チェック ボックスをオンにします。

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>バッテリ電源で実行しているときにセキュリティ インテリジェンスの更新を防止する

PC がワイヤード (有線) 電源に接続されている場合にのみ、保護更新プログラムをダウンロードするようにMicrosoft Defender ウイルス対策を構成できます。

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>グループ ポリシーを使用して、バッテリ電源に関するセキュリティ インテリジェンスの更新を防止する

1. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを選択し、編集用に開きます。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **ポリシー** ]、[ **管理用テンプレート]** の順に選択します。

4. ツリーを展開して **、シグネチャ更新プログラム****Microsoft Defender ウイルス対策コンポーネント** \> **をWindows**\>し、[**バッテリ電源で実行しているときにセキュリティ インテリジェンスの更新を許可する**] を **[無効]** に設定します。 次に [**OK**] を選びます。

この操作により、PC がバッテリ電源に接続されているときに保護更新プログラムがダウンロードされるのを防ぎます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Windows 10でMicrosoft Defender ウイルス対策を更新および管理する](deploy-manage-report-microsoft-defender-antivirus.md)