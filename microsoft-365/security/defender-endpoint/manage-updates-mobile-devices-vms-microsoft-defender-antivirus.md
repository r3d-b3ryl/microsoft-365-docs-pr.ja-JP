---
title: モバイル デバイスの更新方法を定義Microsoft Defender ウイルス対策
description: ラップトップなどのモバイル デバイスを保護更新プログラムで更新する方法Microsoft Defender ウイルス対策管理します。
keywords: 更新プログラム、保護、スケジュールの更新、バッテリー、モバイル デバイス、ノート PC、ノートブック、オプトイン、microsoft update、wsus、override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 212a746e217e071c4770e4830bd101f18bb27f3e
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491183"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

モバイル デバイスと VM では、更新プログラムによるパフォーマンスの影響を受けずに、より多くの構成が必要な場合があります。

これらのデバイスに役立つ 2 つの設定があります。

- WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする
- バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を防止する

次の記事は、次の状況でも役立つ場合があります。
- [スケジュールされたスキャンとキャッチアップ スキャンの構成](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする

Microsoft Update を使用すると、Microsoft Defender ウイルス対策 が企業ネットワークに接続されていない場合、または WSUS 接続がない場合に、モバイル デバイスのセキュリティ インテリジェンスを最新の状態に保つ必要があります。

つまり、Microsoft Update を上書きする WSUS を設定している場合でも、保護更新プログラムを (Microsoft Update 経由で) デバイスに配信できます。

モバイル デバイスで Microsoft Update をオプトインするには、次のいずれかの方法があります。

- グループ ポリシーで設定を変更します。
- VBScript を使用してスクリプトを作成し、ネットワーク内の各コンピューターで実行します。
- [ネットワーク上のすべてのコンピューターを手動で選択する]**メニュー設定します**。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>グループ ポリシーを使用して Microsoft Update にオプトインする

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。

4. ツリーを展開して **、Windows更新Microsoft Defender ウイルス対策** \>  \> **コンポーネントを表示します**。

5. [Microsoft **Update からのセキュリティ インテリジェンス更新プログラムを許可** する] を **[有効] に設定** し  **、[OK] を選択します**。

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>VBScript を使用して Microsoft Update にオプトインする

1. MSDN の記事 [「Opt-In to Microsoft Update」](/windows/win32/wua_sdk/opt-in-to-microsoft-update) の手順を使用して、VBScript を作成します。

2. ネットワーク内の各コンピューターで作成した VBScript を実行します。

### <a name="manually-opt-in-to-microsoft-update"></a>Microsoft Update に手動でオプトインする

1. オ **プトWindowsコンピューター** の **[更新&の** セキュリティ設定] で [更新] を開きます。

2. [詳細設定 **] を** 選択します。

3. [更新プログラムを更新するときに他の Microsoft 製品の更新プログラムを提供する] のチェック **ボックスをオンWindows。**

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を防止する

PC が有線Microsoft Defender ウイルス対策接続されている場合にのみ保護更新プログラムをダウンロードする構成を構成できます。

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>グループ ポリシーを使用してバッテリーの電源に関するセキュリティ インテリジェンスの更新を防止する

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを選択し、編集用に開きます。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。

4. ツリーを展開して **、Windows** 更新Microsoft Defender ウイルス対策を実行し、[バッテリー電源で実行する場合にセキュリティ インテリジェンス更新プログラムを許可する] を [無効] \>  \> に **設定します**。  次に [**OK**] を選びます。

この操作により、PC がバッテリ電源をオンにしている場合に保護更新プログラムがダウンロードされなかから保護されます。

## <a name="related-articles"></a>関連記事

- [更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [更新し、Microsoft Defender ウイルス対策のWindows 10](deploy-manage-report-microsoft-defender-antivirus.md)