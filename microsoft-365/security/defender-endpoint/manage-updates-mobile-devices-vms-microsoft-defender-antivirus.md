---
title: Microsoft Defender Antivirus によるモバイル デバイスの更新方法を定義する
description: Microsoft Defender ウイルス対策保護の更新プログラムを使用して、ラップトップなどのモバイル デバイスを更新する方法を管理します。
keywords: 更新プログラム、保護、スケジュールの更新、バッテリー、モバイル デバイス、ノート PC、ノートブック、オプトイン、microsoft update、wsus、override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 826e1456de2aadf4031a91e30925a1e771d44f70
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765589"
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

Microsoft Update を使用すると、Microsoft Defender ウイルス対策を実行しているモバイル デバイスが企業ネットワークに接続されていない場合や、WSUS 接続がない場合にセキュリティ インテリジェンスを最新の状態に保つ必要があります。 

つまり、Microsoft Update を上書きする WSUS を設定している場合でも、保護更新プログラムを (Microsoft Update 経由で) デバイスに配信できます。

モバイル デバイスで Microsoft Update をオプトインするには、次のいずれかの方法があります。

- グループ ポリシーで設定を変更します。
- VBScript を使用してスクリプトを作成し、ネットワーク内の各コンピューターで実行します。
- [設定] メニューを使用して、ネットワーク上のすべてのコンピューターを手動 **でオプトイン** します。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>グループ ポリシーを使用して Microsoft Update にオプトインする

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。

4. ツリーを Windows コンポーネント **の Microsoft** Defender ウイルス対策  >  **署名更新プログラム**  >  **に展開します**。

5. [Microsoft **Update からのセキュリティ インテリジェンス更新プログラムを許可** する] を **[有効] に設定** し  **、[OK] を選択します**。


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>VBScript を使用して Microsoft Update にオプトインする

1. MSDN の記事 [「Opt-In to Microsoft Update」](/windows/win32/wua_sdk/opt-in-to-microsoft-update) の手順を使用して、VBScript を作成します。

2. ネットワーク内の各コンピューターで作成した VBScript を実行します。

### <a name="manually-opt-in-to-microsoft-update"></a>Microsoft Update に手動でオプトインする

1. [ **更新プログラム] で** **Windows Update &する** コンピューターのセキュリティ設定を開きます。

2. [詳細設定 **] を** 選択します。

3. [Windows の更新時に他の Microsoft 製品の更新 **プログラムを提供する] のチェック ボックスをオンにします**。

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を防止する

Pc が有線電源に接続されている場合にのみ保護更新プログラムをダウンロードする Microsoft Defender ウイルス対策を構成できます。 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>グループ ポリシーを使用してバッテリーの電源に関するセキュリティ インテリジェンスの更新を防止する

1.  グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを選択し、編集用に開きます。

2.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3.  [ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。

4.  ツリーを Windows コンポーネント **の Microsoft** Defender ウイルス対策署名更新プログラムに展開し、[バッテリ電源で実行する場合にセキュリティ インテリジェンス更新プログラムを許可する] を [無効]  >    >  に **設定します**。  次に **[OK]** を選択します。 

この操作により、PC がバッテリ電源をオンにしている場合に保護更新プログラムがダウンロードされなかから保護されます。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Windows 10 で Microsoft Defender ウイルス対策を更新および管理する](deploy-manage-report-microsoft-defender-antivirus.md)