---
title: 'ファイルのインジケーターを作成 '
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュのインジケーターを作成します。
keywords: ファイル, ハッシュ, 管理, 許可, ブロック, ブロック, クリーン, 悪意のある, ファイル ハッシュ, IP アドレス, URL, ドメイン
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 08/10/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f8726c006bac66b18d0e8359fe391a5d6e39ad69
ms.sourcegitcommit: 34910ea9318289d78c35b0e7990238467c05384b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67306432"
---
# <a name="create-indicators-for-files"></a>ファイルのインジケーターを作成 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内での攻撃の伝播をさらに防ぎます。 悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルがわかっている場合は、ブロックできます。 この操作により、組織内のデバイスで読み取り、書き込み、または実行できなくなります。

ファイルのインジケーターを作成するには、次の 3 つの方法があります。

- 設定ページでインジケーターを作成する
- ファイルの詳細ページの [インジケーターの追加] ボタンを使用してコンテキスト インジケーターを作成する
- [Indicator API](ti-indicator.md) を使用してインジケーターを作成する

## <a name="before-you-begin"></a>はじめに

ファイルのインジケーターを作成する前に、次の前提条件を理解しておくことが重要です。

- この機能は、組織が **Microsoft Defender ウイルス対策 (アクティブ モード) を** 使用し、 **クラウドベースの保護が有効になっている場合に** 使用できます。 詳細については、「 [クラウドベースの保護を管理する](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)」を参照してください。

- マルウェア対策クライアントバージョンは、4.18.1901.x 以降である必要があります。 [毎月のプラットフォームとエンジンのバージョンを確認する](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Windows 10バージョン 1703 以降、Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2022 を使用するデバイスでサポートされます。
    
   > [!NOTE]
   > この機能を機能させるには、「[Windows サーバーのオンボード](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)」の手順に従って、Windows Server 2016 R2 と Windows Server 2012 R2 をオンボードする必要があります。 許可、ブロック、および修復アクションを含むカスタム ファイル インジケーターは、 [macOS および Linux 用の強化されたマルウェア対策エンジン機能](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-engine-capabilities-for-linux-and-macos/ba-p/3292003)でも使用できるようになりました。

- ファイルのブロックを開始するには、まず[設定] [で [ブロックまたは許可] 機能をオンにする](advanced-features.md) 必要があります。

この機能は、疑わしいマルウェア (または悪意のあるファイル) が Web からダウンロードされないように設計されています。 現在、.exe ファイルや.dll ファイルを含むポータブル実行可能ファイル (PE) ファイルがサポートされています。 カバレッジは時間の経過と共に延長されます。

> [!IMPORTANT]
> Defender for Endpoint Plan 1 と Defender for Business では、ファイルをブロックまたは許可するインジケーターを作成できます。 Defender for Business では、インジケーターは環境全体に適用され、特定のデバイスにスコープを設定することはできません。

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>設定ページからファイルのインジケーターを作成する

1. ナビゲーション ウィンドウで、[設定 **エンドポイント** \> **インジケーター**] ([**ルール****]** \> の下) を選択します。

2. [ **ファイル ハッシュ** ] タブを選択します。

3. [ **項目の追加]** を選択します。

4. 次の詳細を指定します。
    - インジケーター - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
    - アクション - 実行するアクションを指定し、説明を入力します。
    - スコープ - デバイス グループのスコープを定義します ( [スコープは Defender for Business](../defender-business/mdb-overview.md) では使用できません)。

5. [概要] タブで詳細を確認し、[保存] を選択 **します**。

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>ファイルの詳細ページからコンテキスト インジケーターを作成する

[ファイルに対して応答アクション](respond-file-alerts.md)を実行する場合のオプションの 1 つは、ファイルのインジケーターを追加することです。 ファイルにインジケーター ハッシュを追加するときに、アラートを発生させ、組織内のデバイスがファイルを実行しようとするたびにファイルをブロックすることを選択できます。

インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートは引き続きアラート キューに表示されます。

## <a name="public-preview-alerting-on-file-blocking-actions"></a>パブリック プレビュー: ファイルブロックアクションに関するアラート

> [!IMPORTANT]
> このセクションの情報 (**自動調査と修復エンジンのパブリック プレビュー**) は、製品が商用リリースされる前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

ファイル IOC で現在サポートされているアクションは、許可、監査、ブロック、および修復されます。 ファイルをブロックすることを選択した後、アラートのトリガーが必要かどうかを選択できます。 これにより、セキュリティ運用チームに通知されるアラートの数を制御し、必要なアラートのみが発生することを確認できます。

Microsoft 365 Defenderで、[Settings **Endpoints Indicators** Add New File Hash **]** > \(**新しいファイル ハッシュ****の** >  > 追加\) に移動します。

ファイルをブロックして修復することを選択します。

ファイル ブロック イベントでアラートを生成し、アラート設定を定義するかどうかを選択します。

- アラート のタイトル
- アラートの重大度
- カテゴリ
- 説明
- 推奨処理

:::image type="content" source="images/indicators-generate-alert.png" alt-text="ファイル インジケーターのアラート設定" lightbox="images/indicators-generate-alert.png":::

> [!IMPORTANT]
>
> - 通常、ファイル ブロックは数分以内に適用および削除されますが、30 分以上かかる場合があります。
> - 同じ適用の種類とターゲットを持つ競合するファイル IoC ポリシーがある場合は、より安全なハッシュのポリシーが適用されます。 SHA-256 ファイル ハッシュ IoC ポリシーは SHA-1 ファイル ハッシュ IoC ポリシーに勝ちます。これは、ハッシュの種類が同じファイルを定義する場合、MD5 ファイル ハッシュ IoC ポリシーに勝ちます。 これは、デバイス グループに関係なく常に当てはまります。
> - その他のすべてのケースでは、同じ強制ターゲットを持つ競合するファイル IoC ポリシーがすべてのデバイスとデバイスのグループに適用されている場合、デバイスの場合、デバイス グループ内のポリシーが優先されます。
> - EnableFileHashComputation グループ ポリシーが無効になっている場合、ファイル IoC のブロック精度が低下します。 ただし、有効にすると、デバイスのパフォーマンスに影響を `EnableFileHashComputation` 与える可能性があります。 たとえば、ネットワーク共有からローカル デバイス (特に VPN 接続経由) に大きなファイルをコピーすると、デバイスのパフォーマンスに影響を与える可能性があります。
>
> EnableFileHashComputation グループ ポリシーの詳細については、「 [Defender CSP](/windows/client-management/mdm/defender-csp)」を参照してください。
>
> Linux および macOS 上の Defender for Endpoint でこの機能を構成する方法の詳細については、「 [Linux でファイル ハッシュ計算機能を構成](linux-preferences.md#configure-file-hash-computation-feature) する」と「 [macOS でのファイル ハッシュ計算機能の構成」を](mac-preferences.md#configure-file-hash-computation-feature)参照してください。

## <a name="public-preview-advanced-hunting-capabilities"></a>パブリック プレビュー: 高度なハンティング機能

> [!IMPORTANT]
> このセクションの情報 (**自動調査と修復エンジンのパブリック プレビュー**) は、プレリリース製品に関連しており、商用リリース前に大幅に変更される可能性があります。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

事前の捜索では、応答アクション アクティビティに対してクエリを実行できます。 事前捜索クエリの例を次に示します。

```console
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
Timestamp > ago(30d)
| where AdditionalFields contains "EUS:Win32/CustomEnterpriseBlock!cl"
```

高度な捜索の詳細については、「高度な捜索 [で脅威をプロアクティブに検出する](advanced-hunting-overview.md)」を参照してください。

上記のサンプル クエリで使用できる他のスレッド名を次に示します。

ファイル:

- EUS:Win32/CustomEnterpriseBlock!cl
- EUS:Win32/CustomEnterpriseNoAlertBlock!cl

証明 書：

- EUS:Win32/CustomCertEnterpriseBlock!cl

応答アクション アクティビティは、デバイスタイムラインで表示することもできます。

## <a name="policy-conflict-handling"></a>ポリシー競合処理

証明書と File IoC ポリシー処理の競合は、次の順序に従います。

- アプリケーションコントロールと AppLocker でファイル Windows Defenderが許可されていない場合は、モードポリシー/ポリシーを適用します。その後、**ブロック**
- ファイルが Microsoft Defender ウイルス対策の除外によって許可されている場合は 、**許可** する
- それ以外の場合は、ファイルがブロックによってブロックまたは警告されるか、ファイル IoC に警告されます。その後 **、ブロック/警告**
- 許可ファイル IoC ポリシーによってファイルが許可されている場合は 、**許可** する
- ASR 規則、CFA、AV、SmartScreen、**ブロック** によってファイルがブロックされている場合は、それ以外の場合
- Else **Allow** (AppLocker ポリシー&アプリケーション制御Windows Defender渡します。IoC ルールは適用されません)

>[!NOTE]
> Microsoft Defender ウイルス対策が **[ブロック**] に設定されているが、[Defender for Endpoint] が **[許可]** に設定されている場合、ポリシーは既定で **[許可]** に設定されます。

同じ適用の種類とターゲットを持つ競合するファイル IoC ポリシーがある場合は、より安全な (つまり長い) ハッシュのポリシーが適用されます。 たとえば、両方のハッシュの種類で同じファイルが定義されている場合、SHA-256 ファイル ハッシュ IoC ポリシーは MD5 ファイル ハッシュ IoC ポリシーに勝ちます。

> [!WARNING]
> ファイルと証明書のポリシー競合処理は、ドメイン/URL/IP アドレスのポリシー競合処理とは異なります。

脅威と脆弱性管理のブロック脆弱なアプリケーション機能は、ファイル IoC を適用に使用し、上記の競合処理順序に従います。

### <a name="examples"></a>例

<br>

****

|コンポーネント|コンポーネントの強制|ファイル インジケーターアクション|結果|
|---|---|---|---|
|攻撃対象の縮小ファイル パスの除外|許可|ブロック|ブロック|
|攻撃面の縮小ルール|ブロック|許可|許可|
|Windows Defender Application Control|許可|ブロック|許可|
|Windows Defender Application Control|ブロック|許可|ブロック|
|Microsoft Defender ウイルス対策の除外|許可|ブロック|許可|
|

## <a name="see-also"></a>関連項目

- [インジケーターの作成](manage-indicators.md)
- [IP および URL/ドメインのインジケーターを作成](indicator-ip-domain.md)
- [証明書に基づいてインジケーターを作成する](indicator-certificates.md)
- [インジケーターの管理](indicator-manage.md)
