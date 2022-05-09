---
title: サード パーティのソリューションからの移行中に Microsoft Defender ウイルスのトラブルシューティングを行う
description: Microsoft Defender ウイルス対策に移行するときの一般的なエラーのトラブルシューティング
keywords: イベント, エラー コード, ログ記録, トラブルシューティング, Microsoft Defender ウイルス対策, Windows Defender ウイルス対策, 移行
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 10/19/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 74843a71131ae8f10628dac96086e68e25acb2b0
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788438"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>サード パーティのソリューションからの移行中に Microsoft Defender ウイルスのトラブルシューティングを行う

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

サード パーティのセキュリティ ソリューションからMicrosoft Defender ウイルス対策に移行するときに問題が発生した場合は、ここでヘルプを参照してください。

## <a name="review-event-logs"></a>イベント ログを確認する

1. タスク バーの **[検索** ] アイコンを選択し、イベント ビューアーを検索して、 *イベント ビューアー* アプリを開きます。

    Microsoft Defender ウイルス対策に関する情報については、「**アプリケーションとサービス ログ** \> **Microsoft** \> **Windows Windows Defender**\>」を **参照** してください。

1. そこから、[**操作]** の下にある **[開く**] を選択します。

    詳細ウィンドウからイベントを選択すると、下部のウィンドウの [ **全般** ] タブと [ **詳細** ] タブの下に、イベントに関する詳細情報が表示されます。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender ウイルス対策が開始されない

この問題は、いくつかの異なるイベント ID の形式で発生する可能性があります。これらすべてが同じ根本的な原因を持ちます。

### <a name="associated-event-ids"></a>関連付けられたイベント ID

イベント ID|ログ名|説明|ソース
---|---|---|---
15|アプリケーション|Windows Defender状態が正常にSECURITY_PRODUCT_STATE_OFFに更新されました。|Security Center
5007|Microsoft-Windows-Windows Defender/Operational|Windows Defender ウイルス対策構成が変更されました。 これが予期しないイベントの場合は、マルウェアの結果である可能性があるため、設定を確認する必要があります。 <p> **古い値:** Default\IsServiceRunning = 0x0 <p> **新しい値:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows Defender/Operational|スパイウェアやその他の望ましくない可能性のあるソフトウェアのWindows Defender ウイルス対策スキャンが無効になっています。|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>サード パーティのウイルス対策がインストールされているため、Microsoft Defender ウイルス対策が開始されないかどうかを確認する方法

Windows 10またはWindows 11 デバイスで、Microsoft Defender for Endpointを使用していない場合、サードパーティのウイルス対策がインストールされている場合、Microsoft Defender ウイルス対策は自動的にオフになります。 サード パーティ製のウイルス対策がインストールされたMicrosoft Defender for Endpointを使用している場合、Microsoft Defender ウイルス対策はパッシブ モードで開始され、機能が低下します。

> [!TIP]
> ここで説明したシナリオは、Windows 10とWindows 11にのみ適用されます。 他のバージョンのWindowsは、サード パーティのセキュリティ ソフトウェアと共に実行されるMicrosoft Defender ウイルス対策に[対して異なる応答](microsoft-defender-antivirus-compatibility.md)を持っています。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>サービス アプリを使用してMicrosoft Defender ウイルス対策がオフになっているかどうかを確認する

Services アプリを開くには、タスク バーから **[検索** ] アイコンを選択し、サービスを検索 *します*。 services.msc と入力して、コマンド ラインからアプリを開 *く* こともできます。

Microsoft Defender ウイルス対策に関する情報は、サービス アプリの **[運用Windows Defender**\>] に一覧表示 **されます。** ウイルス対策サービス名は *サービスWindows Defender ウイルス対策* です。

アプリの確認中に、*Windows Defender ウイルス対策 サービス* が手動に設定されていることがわかりますが、このサービスを手動で開始しようとすると、*ローカル コンピューター上のWindows Defender ウイルス対策 サービス サービスが開始され、停止したことを示す警告が表示されます。一部のサービスは、他のサービスまたはプログラムで使用されていない場合、自動的に停止します。*

これは、サードパーティのウイルス対策との互換性を維持するために、Microsoft Defender ウイルス対策が自動的にオフになっていることを示します。

#### <a name="generate-a-detailed-report"></a>詳細なレポートを生成する

現在アクティブなグループ ポリシーに関する詳細なレポートを生成するには、 **管理者として実行** モードでコマンド プロンプトを開き、次のコマンドを入力します。

```console
GPresult.exe /h gpresult.html
```

これにより、 *./gpresult.html* にあるレポートが生成されます。 このファイルを開くと、Microsoft Defender ウイルス対策がオフになっている方法に応じて、次の結果が表示される場合があります。

##### <a name="group-policy-results"></a>グループ ポリシーの結果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>セキュリティ設定がドメインまたはローカル レベルでグループ ポリシー (GPO) を使用して実装されている場合、または System center Configuration Manager (SCCM) を使用する場合

GPResults レポートの見出しの下に、*コンポーネント/Windows Defender ウイルス対策Windows*、Microsoft Defender ウイルス対策がオフになっていることを示す次のエントリのようなものが表示されることがあります。

ポリシー|Setting|GPO を獲得する
---|---|---
Windows Defender ウイルス対策をオフにする|Enabled|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>グループ ポリシー設定 (GPP) を使用してセキュリティ設定を実装する場合

見出しの [*レジストリ] 項目 ([キー パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、 Value name: DisableAntiSpyware)]* の下に、次のようなエントリが表示され、Microsoft Defender ウイルス対策がオフになっていることを示すメッセージが表示されることがあります。

DisableAntiSpyware|-
---|---
GPO を獲得する|Win10-Workstations
結果: 成功|
**全般**|
アクション|Update
**Properties**|
Hive|HKEY_LOCAL_MACHINE
キー パス|SOFTWARE\Policies\Microsoft\Windows Defender
値の名前|DisableAntiSpyware
値の型|REG_DWORD
値データ|0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>レジストリ キーを使用してセキュリティ設定が実装されている場合

レポートには、Microsoft Defender ウイルス対策がオフになっていることを示す次のテキストが含まれている場合があります。

> レジストリ (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (16 進数)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>WindowsまたはWindows サーバー イメージでセキュリティ設定が設定されている場合

想像している管理者が、セキュリティ ポリシー **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** を、 *GPEdit.exe*、 *LGPO.exe*、またはタスク シーケンス内のレジストリを変更してローカルに設定している可能性があります。 [Microsoft Defender ウイルス対策の信頼されたイメージ識別子を構成](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)できます。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Microsoft Defender ウイルス対策をオンに戻す

他のウイルス対策が現在アクティブでない場合、Microsoft Defender ウイルス対策は自動的に有効になります。 Microsoft Defender ウイルス対策が完全な機能で実行されるようにするには、サード パーティのウイルス対策を完全にオフにする必要があります。

> [!WARNING]
> *HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services* で *wdboot*、*wdfilter*、*wdnisdrv*、*wdnissvc*、*および windefend* のWindows Defender開始値を編集することを推奨するソリューションはサポートされておらず、システムのイメージを再作成することが強制される場合があります。

パッシブ モードは、Microsoft Defender for Endpointとサードパーティのウイルス対策をMicrosoft Defender ウイルス対策と共に使用する場合に使用できます。 パッシブ モードではMicrosoft Defender ウイルス対策ファイルをスキャンしてそれ自体を更新できますが、脅威は修復されません。 さらに、[エンドポイント データ損失防止 (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) がデプロイされていない限り、[リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md)による動作監視はパッシブ モードでは使用できません。

Microsoft Defender ウイルス対策が自動的にオフに設定されている場合、もう 1 つの機能 ([制限付き定期的なスキャン](limited-periodic-scanning-microsoft-defender-antivirus.md)と呼ばれます) をエンド ユーザーが使用できます。 この機能により、Microsoft Defender ウイルス対策は、限られた数の検出を使用して、サードパーティのウイルス対策と共に定期的にファイルをスキャンできます。

> [!IMPORTANT]
> エンタープライズ環境では、限られた定期的なスキャンはお勧めしません。 このモードでMicrosoft Defender ウイルス対策を実行するときに使用できる検出、管理、およびレポート機能は、アクティブ モードと比較して減少します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)


### <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)
- [Windows セキュリティ アプリのMicrosoft Defender ウイルス対策](microsoft-defender-security-center-antivirus.md)
