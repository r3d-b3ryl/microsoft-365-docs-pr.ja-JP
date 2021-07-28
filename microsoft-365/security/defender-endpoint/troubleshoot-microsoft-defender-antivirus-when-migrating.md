---
title: サード パーティのソリューションからの移行中に Microsoft Defender ウイルスのトラブルシューティングを行う
description: 移行時の一般的なエラーのトラブルシューティングMicrosoft Defender ウイルス対策
keywords: イベント, エラー コード, ログ記録, トラブルシューティング, Microsoft Defender ウイルス対策, Windows Defender ウイルス対策, 移行
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 80d8ec3a48ea8388d6c1807f2eccb9df334394de
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623362"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>サード パーティのソリューションからの移行中に Microsoft Defender ウイルスのトラブルシューティングを行う

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


サードパーティのセキュリティ ソリューションからセキュリティ ソリューションへの移行中に問題が発生した場合は、ここでMicrosoft Defender ウイルス対策。

## <a name="review-event-logs"></a>イベント ログの確認

タスク バーの [検索]アイコンを選択し、イベント ビューアーを検索して、イベント ビューアー アプリ *を開きます*。

アプリケーションにMicrosoft Defender ウイルス対策については **、「Applications and Services Logs** Microsoft Windows  >    >    >  Windows Defender」**を参照してください**。

そこから、[操作] の **下にある [** 開く] **を選択します**。

詳細ウィンドウからイベントを選択すると、[全般] タブと [詳細] タブの下の下部ウィンドウにイベントの詳細 **が****表示** されます。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender ウイルス対策開始しない

この問題は、複数の異なるイベントの ID の形式で発生する可能性があります。そのすべてが同じ原因を持っています。

### <a name="associated-event-ids"></a>関連付けられたイベントの ID

イベント ID|ログ名|説明|ソース
---|---|---|---
15|アプリケーション|更新されたWindows Defender状態が正常に更新SECURITY_PRODUCT_STATE_OFF。|セキュリティ センター
5007|Microsoft-Windows-Windows Defender/運用|Windows Defender ウイルス対策構成が変更されました。  予期しないイベントの場合は、マルウェアの結果である可能性がある設定を確認する必要があります。 <p> **古い値:** Default\IsServiceRunning = 0x0 p> 新しい値 **:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows Defender/運用|Windows Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアのスキャンが無効になります。|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>サードパーティのウイルス対策Microsoft Defender ウイルス対策がインストールされたため、ユーザーが起動しないかを確認する方法

デバイスWindows 10 Microsoft Defender for Endpoint を使用していない場合に、サードパーティのウイルス対策がインストールされている場合は、Microsoft Defender ウイルス対策が自動的にオフになります。 サードパーティのウイルス対策がインストールされている Microsoft Defender for Endpoint を使用している場合、Microsoft Defender ウイルス対策モードで起動し、機能が低下します。

> [!TIP]
> 説明したシナリオは、次のシナリオにのみWindows 10。 他のバージョンのWindows[サードパーティ](microsoft-defender-antivirus-compatibility.md)のセキュリティ ソフトウェアとMicrosoft Defender ウイルス対策に対する応答が異なります。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>サービス アプリを使用して、Microsoft Defender ウイルス対策がオフになっているか確認する

サービス アプリを開く場合は、タスク バーから **[検索** ] アイコンを選択し、サービスを検索 *します*。 services.msc と入力して、コマンド ラインから *アプリを開く方法もあります*。

サービスに関Microsoft Defender ウイルス対策情報は、[運用] の [サービス] アプリ **Windows Defender**  >  **表示されます**。 ウイルス対策サービス名はサービス *Windows Defender ウイルス対策です*。

アプリの確認中に *、Windows Defender ウイルス対策 Service* が手動に設定されている場合がありますが、このサービスを手動で開始しようとすると、ローカル コンピューター上の Windows Defender ウイルス対策 Service サービスが開始してから停止したという警告が表示されます。 *一部のサービスは、他のサービスやプログラムで使用されていない場合に自動的に停止します。*

これは、サードパーティのMicrosoft Defender ウイルス対策との互換性を維持するために、ユーザーが自動的にオフになっていることを示します。

#### <a name="generate-a-detailed-report"></a>詳細レポートの生成

管理モードでコマンド プロンプトを開き、次のコマンドを入力すると、現在アクティブなグループ ポリシーに関する詳細なレポートを生成できます。

```powershell
GPresult.exe /h gpresult.html
```

これにより、./gpresult.html にある *レポートが生成されます*。 このファイルを開き、次の結果が表示される場合があります。このファイルのMicrosoft Defender ウイルス対策に応じて異なる場合があります。

##### <a name="group-policy-results"></a>グループ ポリシーの結果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>セキュリティ設定がドメインまたはローカル レベルのグループ ポリシー (GPO) または System Center Configuration Manager (SCCM) を介して実装されている場合

GPResults レポート内の見出し *Windows Components/Windows Defender ウイルス対策* の下に、Microsoft Defender ウイルス対策 がオフになっていることを示す次のエントリのようなものが表示される場合があります。

ポリシー|Setting|GPO を獲得する
---|---|---
[オフにする] Windows Defender ウイルス対策|有効|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>グループ ポリシーの基本設定 (GPP) を使用してセキュリティ設定を実装する場合

見出しの下にレジストリ アイテム (キー パス *: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、 Value name: DisableAntiSpyware)* が表示され、Microsoft Defender ウイルス対策 がオフになっていることを示す次のエントリが表示される場合があります。

DisableAntiSpyware|-
---|---
GPO を獲得する|Win10-Workstations
結果: 成功|
**全般**|
アクション|Update
**プロパティ**|
ハイブ|HKEY_LOCAL_MACHINE
キー パス|SOFTWARE\Policies\Microsoft\Windows Defender
値の名前|DisableAntiSpyware
値の型|REG_DWORD
値データ|0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>セキュリティ設定がレジストリ キーを使用して実装されている場合

レポートには、次のテキストが含まれている場合があります。このMicrosoft Defender ウイルス対策オフになっていることを示します。

> レジストリ (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (16 進数)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>セキュリティ設定がサーバーイメージまたはサーバー イメージWindows設定Windows場合

想像上の管理者は、セキュリティ ポリシー **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** を *GPEdit.exe*、 *LGPO.exe* 経由でローカルに設定するか、タスク シーケンスでレジストリを変更している可能性があります。 信頼済[みイメージ識別子を構成](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)Microsoft Defender ウイルス対策。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>電源Microsoft Defender ウイルス対策オンにする

Microsoft Defender ウイルス対策ウイルス対策が現在アクティブにされていない場合は、自動的に有効になります。 サードパーティのウイルス対策を完全にオフにし、完全なMicrosoft Defender ウイルス対策を実行する必要があります。

> [!WARNING]
> HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Servicesの wdboot、wdfilter、wdnisdrv、wdnisdrv、および *windefend* の Windows Defender 開始値を編集する方法はサポートされていないため、システムのイメージを変更する必要があります。  

パッシブ モードは、Microsoft Defender for Endpoint の使用を開始し、サードパーティのウイルス対策と一緒に使用する場合Microsoft Defender ウイルス対策。 パッシブ モードでは、Microsoft Defender はファイルをスキャンしてそれ自体を更新できますが、脅威を修復しません。 さらに、リアルタイム保護による動作[](configure-real-time-protection-microsoft-defender-antivirus.md)監視は、エンドポイント データ損失防止[(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)が展開されていない限り、パッシブ モードでは使用できません。

制限付き[定期的スキャンと](limited-periodic-scanning-microsoft-defender-antivirus.md)呼ばれる別の機能は、ユーザーが自動的にオフMicrosoft Defender ウイルス対策に設定されている場合に使用できます。 この機能により、Microsoft Defender ウイルス対策を使用して、サードパーティのウイルス対策と一緒に定期的にファイルをスキャンできます。

> [!IMPORTANT]
> エンタープライズ環境では、限定的な定期的なスキャンは推奨されません。 このモードでアプリを実行するときに使用できる検出、管理、およびMicrosoft Defender ウイルス対策機能は、アクティブ モードと比較して減少します。

### <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)
- [Microsoft Defender ウイルス対策アプリでWindows セキュリティする](microsoft-defender-security-center-antivirus.md)
