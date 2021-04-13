---
title: サード パーティ製ソリューションからの移行中に Microsoft Defender ウイルス対策のトラブルシューティングを行う
description: Microsoft Defender ウイルス対策に移行する際の一般的なエラーのトラブルシューティング
keywords: イベント, エラー コード, ログ記録, トラブルシューティング, Microsoft Defender ウイルス対策, Windows Defender ウイルス対策, 移行
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2ca486b86c24e18ae08753b5e88f2eb42986dddf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691360"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>サード パーティ製ソリューションからの移行中に Microsoft Defender ウイルス対策のトラブルシューティングを行う

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


サードパーティのセキュリティ ソリューションから Microsoft Defender Antivirus への移行中に問題が発生した場合は、ここでヘルプを参照してください。

## <a name="review-event-logs"></a>イベント ログの確認

タスク バーの [検索]アイコンを選択し、イベント ビューアーを検索して、イベント ビューアー アプリ *を開きます*。

Microsoft Defender ウイルス対策に関する情報は、「**アプリケーション** とサービス ログ Microsoft Windows のログ」の下  >    >    >  Windows Defender。 

そこから、[操作] の **下にある [** 開く] **を選択します**。

詳細ウィンドウからイベントを選択すると、[全般] タブと [詳細] タブの下の下部ウィンドウにイベントの詳細 **が****表示** されます。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender ウイルス対策が開始しない

この問題は、複数の異なるイベントの ID の形式で発生する可能性があります。そのすべてが同じ原因を持っています。

### <a name="associated-event-ids"></a>関連付けられたイベントの ID

 イベント ID | ログ名 | 説明 | ソース
-|-|-|-
15  | アプリケーション | 更新されたWindows Defender状態が正常に更新SECURITY_PRODUCT_STATE_OFF。 | セキュリティ センター
5007 | Microsoft-Windows-Windows Defender/運用 | Windows Defenderの構成が変更されました。  予期しないイベントの場合は、マルウェアの結果である可能性がある設定を確認する必要があります。<br /><br />**古い値:** Default\IsServiceRunning = 0x0<br />**新しい値:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/運用 | Windows Defenderスパイウェアなどの望ましくない可能性があるソフトウェアのウイルス対策スキャンが無効になります。 | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>サード パーティ製ウイルス対策がインストールされたため、Microsoft Defender Antivirus が起動しないかを確認する方法

Windows 10 デバイスで、Microsoft Defender for Endpoint を使用していない場合、サードパーティのウイルス対策がインストールされている場合、Microsoft Defender ウイルス対策は自動的に無効になります。 サードパーティのウイルス対策がインストールされている Microsoft Defender for Endpoint を使用している場合、Microsoft Defender Antivirus はパッシブ モードで起動し、機能が低下します。

> [!TIP]
> 説明したシナリオは、Windows 10 にのみ適用されます。 他のバージョンの Windows[](microsoft-defender-antivirus-compatibility.md)では、サードパーティのセキュリティ ソフトウェアと共に実行されている Microsoft Defender ウイルス対策に対する応答が異なります。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>サービス アプリを使用して Microsoft Defender ウイルス対策が無効になっているか確認する

サービス アプリを開く場合は、タスク バーから **[検索** ] アイコンを選択し、サービスを検索 *します*。 services.msc と入力して、コマンド ラインから *アプリを開く方法もあります*。

Microsoft Defender ウイルス対策に関する情報は、[運用]の [サービス] アプリWindows Defender  >  **されます**。 ウイルス対策サービス名はウイルス *Windows Defenderサービスです*。

アプリの確認中に *、Windows Defender ウイルス* 対策サービスが手動に設定されている場合がありますが、このサービスを手動で開始しようとすると、ローカル コンピューターの Windows Defender ウイルス対策サービス サービスが開始され、停止したという警告が表示されます。 *一部のサービスは、他のサービスやプログラムで使用されていない場合に自動的に停止します。*

これは、サードパーティのウイルス対策との互換性を維持するために Microsoft Defender ウイルス対策が自動的にオフになっていることを示します。

#### <a name="generate-a-detailed-report"></a>詳細レポートの生成

管理モードでコマンド プロンプトを開き、次のコマンドを入力すると、現在アクティブなグループ ポリシーに関する詳細なレポートを生成できます。

```powershell
GPresult.exe /h gpresult.html
```

これにより、./gpresult.html にある *レポートが生成されます*。 このファイルを開き、Microsoft Defender ウイルス対策がオフになっている方法に応じて、次の結果が表示される場合があります。

##### <a name="group-policy-results"></a>グループ ポリシーの結果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>セキュリティ設定がドメインまたはローカル レベルのグループ ポリシー (GPO) または System Center Configuration Manager (SCCM) を介して実装されている場合

GPResults レポートの見出しの下にある *[Windows コンポーネント/Windows Defender ウイルス* 対策] では、Microsoft Defender ウイルス対策がオフになっていることを示す次のエントリのようなものが表示される場合があります。

ポリシー | 設定 | GPO を獲得する
-|-|-
ウイルス対策をWindows Defenderする | Enabled | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>グループ ポリシーの基本設定 (GPP) を使用してセキュリティ設定を実装する場合

見出しの下にあるレジストリ アイテム (キー パス *: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、 Value name: DisableAntiSpyware)* では、Microsoft Defender Antivirus がオフになっていることを示す次のエントリのようなものが表示される場合があります。

DisableAntiSpyware | -
-|-
GPO を獲得する | Win10-Workstations
結果: 成功 | 
**全般** | 
Action | Update
**プロパティ** | 
ハイブ | HKEY_LOCAL_MACHINE
キー パス | SOFTWARE\Policies\Microsoft\Windows Defender
値の名前 | DisableAntiSpyware
値の型 | REG_DWORD
値データ | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>セキュリティ設定がレジストリ キーを使用して実装されている場合

レポートには、Microsoft Defender ウイルス対策が無効になっていることを示す次のテキストが含まれている場合があります。
 
> レジストリ (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (16 進数)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Windows または Windows Server イメージでセキュリティ設定が設定されている場合

想像上の管理者は、セキュリティ ポリシー **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** を *GPEdit.exe*、 *LGPO.exe* 経由でローカルに設定するか、タスク シーケンスでレジストリを変更している可能性があります。 Microsoft Defender [ウイルス対策の信頼済みイメージ識別子](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) を構成できます。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Microsoft Defender ウイルス対策を有効に戻す

他のウイルス対策が現在アクティブにされていない場合、Microsoft Defender ウイルス対策は自動的に有効になります。 Microsoft Defender Antivirus を完全な機能で実行するには、サードパーティのウイルス対策を完全にオフにする必要があります。

> [!WARNING]
> HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Servicesの wdboot、wdfilter、wdnisdrv、wdnisdrv、*および* *windefend* の Windows Defender の開始値を編集するソリューションはサポートされていないため、強制的にシステムを再イメージ化する可能性があります。   

パッシブ モードは、Microsoft Defender for Endpoint の使用を開始し、Microsoft Defender Antivirus と共にサードパーティのウイルス対策を開始する場合に使用できます。 パッシブ モードでは、Microsoft Defender はファイルをスキャンしてそれ自体を更新できますが、脅威を修復しません。 さらに、リアルタイム保護による動作[](configure-real-time-protection-microsoft-defender-antivirus.md)監視は、エンドポイント データ損失防止[(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)が展開されていない限り、パッシブ モードでは使用できません。

Microsoft Defender Antivirus [が自動的に](limited-periodic-scanning-microsoft-defender-antivirus.md)オフに設定されている場合は、制限付き定期的なスキャンと呼ばれるもう 1 つの機能をエンド ユーザーが利用できます。 この機能を使用すると、Microsoft Defender Antivirus は、限られた数の検出を使用して、サードパーティのウイルス対策と一緒に定期的にファイルをスキャンできます。

> [!IMPORTANT]
> エンタープライズ環境では、限定的な定期的なスキャンは推奨されません。 このモードで Microsoft Defender ウイルス対策を実行するときに使用できる検出、管理、およびレポート機能は、アクティブ モードと比較して低下します。

### <a name="see-also"></a>関連項目

* [Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)
* [Windows セキュリティ アプリの Microsoft Defender ウイルス対策](microsoft-defender-security-center-antivirus.md)