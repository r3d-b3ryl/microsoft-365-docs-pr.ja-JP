---
title: 改ざん防止機能を使用してセキュリティ設定を保護する
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: 改ざん防止を使用して、悪意のあるアプリが重要なセキュリティ設定を変更できないようにします。
keywords: マルウェア, Defender, ウイルス対策, 改ざん防止
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: f668efd6c205d67d5aaf4ffa86fae6933f9a257a
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66686143"
---
# <a name="protect-security-settings-with-tamper-protection"></a>改ざん防止機能を使用してセキュリティ設定を保護する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

改ざん防止は、次のいずれかのバージョンの Windows を実行しているデバイスで使用できます。

- Windows 11
- Windows 11 Enterprise multi-session 
- Windows 10
- Windows 10 Enterprise マルチセッション
- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> Windows Server 2012 R2 の改ざん保護は、最新の統合ソリューション パッケージを使用してオンボードされたデバイスで使用できます。 詳細については、「[Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints)」を参照してください。

## <a name="overview"></a>概要

サイバー攻撃の種類によっては、悪いアクターがマシンでウイルス対策保護などのセキュリティ機能を無効にしようとします。 悪意のあるアクターは、データへのアクセスを容易にしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にすることを好みます。 改ざん防止は、このようなことが発生するのを防ぐのに役立ちます。 改ざん防止により、悪意のあるアプリは次のようなアクションを実行できなくなります。

- ウイルスおよび脅威の保護の無効化
- リアルタイム保護の無効化
- 動作の監視の無効化
- IOfficeAntivirus (IOAV) などのウイルス対策保護を無効にする
- クラウド配信の保護の無効化
- セキュリティ インテリジェンスの更新プログラムの削除
- 検出された脅威に対する自動アクションを無効にする
- Windows セキュリティ アプリでの通知の抑制
- アーカイブファイルとネットワーク ファイルのスキャンを無効にする

### <a name="how-it-works"></a>メカニズム

改ざん防止は、基本的に Microsoft Defender ウイルス対策をセキュリティで保護された既定値にロックし、次のようなアプリや方法を使用してセキュリティ設定が変更されないようにします。

- Windows デバイスのレジストリ エディターで設定を構成する
- PowerShell コマンドレットを使用した設定の変更
- グループ ポリシーを使用したセキュリティ設定の編集または削除

改ざん防止では、セキュリティ設定を表示できません。 また、改ざん防止は、Microsoft 以外のウイルス対策アプリがWindows セキュリティ アプリに登録する方法には影響しません。 組織で Windows 10 Enterprise E5 を使用している場合、個々のユーザーは改ざん防止設定を変更できません。そのような場合、改ざん保護はセキュリティ チームによって管理されます。

### <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

|このタスクを実行するには...|このセクションを参照してください。..|
|---|---|
|テナント全体の改ざん保護を管理する <p> Microsoft 365 Defender ポータルを使用して改ざん防止を有効または無効にする|[Microsoft 365 Defenderを使用して組織の改ざん防止を管理する](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)|
|組織内の改ざん防止設定を微調整する <p> 改ざん防止を有効または無効にするには、Intune (Microsoft エンドポイント マネージャー) を使用します。 この方法を使用して、一部またはすべてのユーザーの改ざん防止を構成できます。|[Microsoft エンドポイント マネージャーを使用して組織の改ざん防止を管理する](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)|
|Configuration Managerを使用して組織の改ざん防止をオン (またはオフ) にする|[Configuration Managerバージョン 2006 でテナントアタッチを使用して組織の改ざん保護を管理する](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)|
|個々のデバイスの改ざん防止をオン (またはオフ) にする|[個々のデバイスで改ざん防止を管理する](#manage-tamper-protection-on-an-individual-device)|
|デバイスでの改ざんの試行に関する詳細を表示する|[改ざんの試行に関する情報を表示する](#view-information-about-tampering-attempts)|
|セキュリティに関する推奨事項を確認する|[セキュリティに関する推奨事項を確認する](#review-your-security-recommendations)|
|よく寄せられる質問の一覧 (FAQ) を確認する|[FAQ を参照する](#view-information-about-tampering-attempts)|

## <a name="potential-dependency-on-cloud-protection"></a>クラウド保護に対する潜在的な依存関係  
  
改ざん防止を有効にするために使用する方法または管理ツールによっては、 [クラウド配信保護](cloud-protection-microsoft-defender-antivirus.md) に依存している場合があります。クラウド配信保護は、クラウド保護または Microsoft Advanced Protection Service (MAPS) とも呼ばれます。

次の表に、メソッド、ツール、依存関係の詳細を示します。

| 改ざん防止を有効にする方法 | クラウド保護への依存 |
|---|---|
|Microsoft Intune|不要|
|テナントアタッチを使用した Microsoft Endpoint Configuration Manager|不要|
|Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com))|はい|

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用して組織の改ざん防止を管理する

改ざん防止は、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) を使用して、テナントに対して有効または無効にすることができます。 注意すべき点をいくつか次に示します。

- 現在、新しいデプロイでは、Microsoft 365 Defender ポータルで改ざん防止を管理するオプションが既定でオンになっています。 既存のデプロイの場合、改ざん保護はオプトインベースで利用できます。 オプトインするには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[Settings **Endpoints** Advanced features Tamper protection] (エンドポイントの\>**高度な機能** \> **の改ざん防止****の設定)** \> を選択します。
- Microsoft 365 Defender ポータルを使用して改ざん防止を管理する場合は、Intuneまたはテナント接続方法を使用する必要はありません。
- Microsoft 365 Defender ポータルで改ざん防止を管理すると、テナント全体に設定が適用され、Windows 10、Windows 10 Enterpriseマルチセッション、Windows 11、Windows 11 Enterpriseを実行しているすべてのデバイスに影響します。 マルチセッション、Windows Server 2012 R2、Windows Server 2016、Windows Server 2019 または Windows Server 2022。 改ざん防止を微調整するには (一部のデバイスでは改ざん保護をオンにし、他のデバイスでは改ざん防止をオンにするなど)、[Microsoft エンドポイント マネージャー](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)または[テナントアタッチConfiguration Manager](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)を使用します。
- ハイブリッド環境がある場合、Intuneで構成された改ざん防止設定は、Microsoft 365 Defender ポータルで構成された設定よりも優先されます。

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで改ざん防止を管理するための要件

- グローバル管理者、セキュリティ管理者、セキュリティ操作など、適切な [アクセス許可](/microsoft-365/security/defender-endpoint/assign-portal-access) が割り当てられている必要があります。

- Windows デバイスは、次のいずれかのバージョンの Windows を実行している必要があります。
  
  - Windows 11
  - Windows 11 Enterprise multi-session 
  - Windows 10
  - Windows 10 Enterprise マルチセッション
  - Windows Server 2022
  - Windows Server 2019
  - Windows Server バージョン 1803 以降
  - Windows Server 2016
  - Windows Server 2012 R2

リリースの詳細については、[リリース情報Windows 10](/windows/release-health/release-information)参照してください。

- デバイスを[Microsoft Defender for Endpointにオンボードする](/microsoft-365/security/defender-endpoint/onboarding)必要があります。
- デバイスは、マルウェア対策プラットフォームバージョン `4.18.2010.7` (またはそれ以上) とマルウェア対策エンジンバージョン `1.1.17600.5` (またはそれ以上) を使用している必要があります。 ([Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用します](manage-updates-baselines-microsoft-defender-antivirus.md)。
- [クラウド配信の保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。

> [!NOTE]
> Microsoft 365 Defender ポータルを使用して改ざん保護を有効にすると、改ざん防止の有効な状態を制御できるように、クラウド配信の保護が必要になります。  
> 2021 年 11 月の更新プログラム (プラットフォーム バージョン`4.18.2111.5`) 以降、デバイスに対してクラウド配信保護が有効にされておらず、Microsoft 365 Defender ポータルで改ざん防止が有効になっている場合、改ざん防止と共にそのデバイスに対してクラウド配信保護が自動的に有効になります。   

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで改ざん防止をオン (またはオフ) にする

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="Microsoft 365 Defender ポータルで改ざん防止を有効にする" lightbox="../../media/mde-turn-tamperprotectionon.png":::

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. [**設定エンドポイント] を**\>選択 **します**。

3. **一般的** \> **な高度な機能** に移動し、改ざん防止を有効にします。

## <a name="manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーを使用して組織の改ざん防止を管理する

組織で Microsoft エンドポイント マネージャー (MEM) を使用している場合は、Microsoft エンドポイント マネージャー管理センター () で組織の改ざん防止をオン ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)またはオフ) にすることができます。 改ざん防止設定を微調整する場合は、Intuneを使用します。 たとえば、一部のデバイスで改ざん防止を有効にする場合は、すべてではなく、Intuneを使用します。

### <a name="requirements-for-managing-tamper-protection-in-endpoint-manager"></a>エンドポイント マネージャーで改ざん防止を管理するための要件

- デバイスを[Microsoft Defender for Endpointにオンボードする](/microsoft-365/security/defender-endpoint/onboarding)必要があります。
- グローバル管理者、セキュリティ管理者、セキュリティ操作など、適切な [アクセス許可](/microsoft-365/security/defender-endpoint/assign-portal-access) が割り当てられている必要があります。
- 組織では[、Microsoft エンドポイント マネージャーを使用してデバイスを管理します](/mem/endpoint-manager-getting-started)。 (Microsoft エンドポイント マネージャー (MEM) ライセンスが必要です。MEM は、Microsoft 365 E3/E5、Enterprise Mobility + Security E3/E5、Microsoft 365 Business Premium、Microsoft 365 F1/F3、Microsoft 365 Government G3/G5、および対応する教育ライセンスに含まれています)。
- Windows デバイスは、[Windows 11または 1709、1803](/lifecycle/announcements/revised-end-of-service-windows-10-1709)、[1809](/lifecycle/announcements/windows-server-1803-end-of-servicing) 以降Windows 10実行されている必要があります[](/windows/release-health/status-windows-10-1809-and-windows-server-2019)。 (リリースの詳細については、[リリース情報Windows 10](/windows/release-health/release-information)参照してください。
- [セキュリティ インテリジェンス](https://www.microsoft.com/wdsi/definitions)がバージョン 1.287.60.0 (またはそれ以降) に更新された Windows セキュリティを使用している必要があります。
- デバイスは、マルウェア対策プラットフォーム バージョン 4.18.1906.3 (またはそれ以降) とマルウェア対策エンジンバージョン `1.1.15500.X` (またはそれ以降) を使用している必要があります。 ([Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用します](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="turn-tamper-protection-on-or-off-in-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーで改ざん防止をオン (またはオフ) にする

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="Intuneで改ざん防止を有効にする" lightbox="images/turnontamperprotectinmem.png":::

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**エンドポイント セキュリティ** \> **ウイルス対策** に移動し、[**+ ポリシーの作成**] を選択します。

   - **[プラットフォーム**] ボックスの一覧 **で、Windows 10以降を** 選択します。
   - **[プロファイル**] ボックスの一覧 **で、[Windows セキュリティエクスペリエンス**] を選択します。

2. 次の設定を含むプロファイルを作成します。

    - **改ざん防止を有効にして Microsoft Defender が無効にならないようにする: 有効にする**

3. プロファイルを 1 つ以上のグループに割り当てます。
 
### <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Configuration Managerバージョン 2006 で組織の改ざん保護を管理する

[バージョン 2006 のConfiguration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)を使用している場合は、Windows 10、Windows 10 Enterpriseマルチセッション、Windows 11、Windows 11 Enterpriseマルチセッションで改ざん防止設定を管理できます。*テナントアタッチ* と呼ばれるメソッドを使用して、R2、Windows Server 2016、Windows Server 2019、Windows Server 2022 をWindows Server 2012します。 テナント接続を使用すると、オンプレミス専用のConfiguration Manager デバイスを Microsoft エンドポイント マネージャー管理センターに同期し、エンドポイント セキュリティ構成ポリシーをオンプレミス コレクション&デバイスに配信できます。

> [!NOTE]
> この手順を使用すると、Windows 10、Windows 10 Enterprise マルチセッション、Windows 11、Windows 11 Enterprise マルチセッション、Windows Server 2019、Windows Server 2022 を実行しているデバイスに改ざん防止を拡張できます。 この手順で説明されているリソースの前提条件とその他の情報を確認してください。 最新の統合ソリューション [バージョン 2203 を実行する Windows Server 2012 R2 では、Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2203)が必要です。

1. テナントアタッチを設定します。 詳細については、「 [はじめに: 管理センターからエンドポイント セキュリティ ポリシーを作成してデプロイする」を参照してください](/mem/configmgr/tenant-attach/endpoint-security-get-started)。

2. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**エンドポイント セキュリティ** \> **ウイルス対策** に移動し、[**+ ポリシーの作成**] を選択します。

   - **プラットフォーム** の一覧で、**Windows 10、Windows 11、Windows Server (ConfigMgr)** を選択します。
   - **プロファイル** の一覧で、**Windows セキュリティエクスペリエンス (プレビュー)** を選択します。

3. デバイス コレクションにポリシーを展開します。

#### <a name="need-help-with-this-method"></a>このメソッドに関するヘルプが必要ですか?

以下のリソースを参照してください。

- [Microsoft IntuneのWindows セキュリティ エクスペリエンス プロファイルの設定](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Tech Community ブログ: Configuration Manager テナント接続クライアントの改ざん防止の発表](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>個々のデバイスで改ざん防止を管理する

> [!NOTE]
> 改ざん防止は、レジストリを介して Microsoft Defender ウイルス対策の設定を変更しようとする試みをブロックします。
> 改ざん防止が、これらの設定を変更する Microsoft 以外のセキュリティ製品やエンタープライズ インストール スクリプトに干渉しないようにするには、**Windows セキュリティ** に移動し、**セキュリティ インテリジェンス** をバージョン 1.287.60.0 以降に更新します。 ( [セキュリティ インテリジェンスの更新プログラムを](https://www.microsoft.com/wdsi/definitions)参照してください。)この更新プログラムを実行すると、改ざん防止によってレジストリ設定が保護され続け、ログはエラーを返さずに変更を試みます。

ホーム ユーザーであるか、セキュリティ チームによって管理されている設定の対象になっていない場合は、Windows セキュリティ アプリを使用して改ざん防止を管理できます。 改ざん防止などのセキュリティ設定を変更するには、デバイスに対する適切な管理者アクセス許可が必要です。

Windows セキュリティ アプリに表示される内容は次のとおりです。

:::image type="content" source="images/tamperprotectionturnedon.png" alt-text="Windows 10 Homeで改ざん防止を有効にする" lightbox="images/tamperprotectionturnedon.png":::

1. **[スタート] を** 選択し、セキュリティの入力を開始 *します*。 検索結果で [**Windows セキュリティ**] を選択します。

2. **[ウイルス&脅威対策** のウイルス\>**&脅威の保護設定] を選択します**。

3. **[改ざん防止****] を [オン] または [オフ] に** 設定 **します**。

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>R2、2016、または Windows バージョン 1709、1803、または 1809 Windows Server 2012使用していますか?

最新の統合ソリューション、Windows Server 2016、Windows 10 バージョン 1709、1803、または [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) を使用して Windows Server 2012 R2 を使用している場合、Windows セキュリティ アプリに **改ざん防止** は表示されません。 代わりに、PowerShell を使用して、改ざん保護が有効になっているかどうかを判断できます。

Windows Server 2016では、改ざん防止が有効になっている場合、設定アプリはリアルタイム保護の状態を正確に反映しません。

#### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>PowerShell を使用して、改ざん防止とリアルタイム保護が有効になっているかどうかを判断する

1. Windows PowerShell アプリを開きます。

2. [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell コマンドレットを使用します。

3. 結果の一覧で、 `IsTamperProtected` 検索または検索します `RealTimeProtectionEnabled`。 ( *true* の値は、改ざん保護が有効になっていることを意味します)。

## <a name="view-information-about-tampering-attempts"></a>改ざんの試行に関する情報を表示する

改ざんの試行は、通常、より大きなサイバー攻撃を示しています。 不適切なアクターは、セキュリティ設定を永続化して検出され続ける方法として変更しようとします。 組織のセキュリティ チームの一員である場合は、そのような試行に関する情報を表示し、脅威を軽減するための適切なアクションを実行できます。

改ざんの試行が検出されると、[Microsoft 365 Defender ポータル](/microsoft-365/security/defender-endpoint/portal-overview) ([https://security.microsoft.com](https://security.microsoft.com)) でアラートが発生します。

[Microsoft Defender for Endpointでエンドポイントの検出と応答](overview-endpoint-detection-response.md)、[高度な捜索](advanced-hunting-overview.md)機能を使用して、セキュリティ運用チームはそのような試みを調査して対処できます。

## <a name="review-your-security-recommendations"></a>セキュリティに関する推奨事項を確認する

改ざん防止は [、脅威&脆弱性管理機能](next-gen-threat-and-vuln-mgt.md) と統合されます。 [セキュリティに関する推奨事項には、](tvm-security-recommendation.md) 改ざん防止が有効になっていることを確認することが含まれます。 たとえば、 *改ざん* を検索できます。 結果で、[ **改ざん防止を有効にする]** を選択して詳細を確認し、有効にすることができます。

脅威&脆弱性管理の詳細については、「[ダッシュボードの分析情報 - 脅威と脆弱性の管理](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management)」を参照してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>改ざん防止を構成できる Windows のバージョンはどれですか?

- Windows 11
- Windows 11 Enterprise multi-session
- Windows 10 OS [1709](/lifecycle/announcements/revised-end-of-service-windows-10-1709)、[1803](/lifecycle/announcements/windows-server-1803-end-of-servicing)、[1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 以降と[共にMicrosoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)。
- Windows 10 Enterprise マルチセッション
  
テナント接続で Configuration Manager バージョン 2006 を使用している場合は、改ざん防止を Windows Server 2012 R2、Windows Server 2016、Windows Server 2019、Windows Server 2022 に拡張できます。 「 [テナントのアタッチ: 管理センターからエンドポイント セキュリティウイルス対策ポリシーを作成して展開する (プレビュー)」](/mem/configmgr/tenant-attach/deploy-antivirus-policy)を参照してください。

### <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>改ざん防止は、Windows セキュリティ アプリでの Microsoft 以外のウイルス対策登録に影響しますか?

いいえ。 Microsoft 以外のウイルス対策オファリングは、引き続きWindows セキュリティ アプリケーションに登録されます。

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>デバイスで Microsoft Defender ウイルス対策がアクティブでない場合はどうなりますか?

Microsoft Defender for Endpointにオンボードされているデバイスでは、Microsoft Defender ウイルス対策がパッシブ モードで実行されます。 このような場合、改ざん保護は引き続きサービスとその機能を保護します。

### <a name="how-do-i-turn-tamper-protection-on-or-off"></a>改ざん防止操作方法オンまたはオフにしますか?

ホーム ユーザーの場合は、「個々の [デバイスで改ざん防止を管理する」を参照してください](#manage-tamper-protection-on-an-individual-device)。

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)を使用している組織の場合は、他のエンドポイント保護機能を管理する方法と同様に、Intuneで改ざん防止を管理できる必要があります。 この記事の次のセクションを参照してください。

- [Microsoft エンドポイント マネージャーを使用して改ざん防止を管理する](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)
- [Microsoft 365 Defender ポータルを使用して改ざん防止を管理する](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>Intuneで改ざん防止を構成すると、グループ ポリシーを使用して Microsoft Defender ウイルス対策を管理する方法にどのような影響がありますか?

現在Intuneを使用して改ざん防止を構成および管理している場合は、Intuneを引き続き使用する必要があります。 

グループ ポリシーは改ざん防止には適用されません。 グループ ポリシーを使用して Microsoft Defender ウイルス対策設定に加えられた変更は、改ざん防止が有効になっている場合、または改ざん防止がIntuneで構成されている場合は無視されます。

### <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>改ざん防止を構成するためにMicrosoft Intuneを使用する場合、組織全体にのみ適用されますか?

Intuneを使用して改ざん防止を柔軟に構成できます。 組織全体を対象にすることも、特定のデバイスとユーザー グループを選択することもできます。

### <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Managerで改ざん防止を構成できますか?

テナント接続を使用している場合は、Microsoft Endpoint Configuration Managerを使用できます。 以下のリソースを参照してください。

- [Configuration Managerバージョン 2006 で組織の改ざん保護を管理する](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Tech Community ブログ: Configuration Manager テナントアタッチ クライアントの改ざん防止の発表](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Windows E3 登録があります。 Intuneで改ざん防止の構成を使用できますか?

現在、Intuneでの改ざん保護の構成は、[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)をお持ちのお客様のみが使用できます。

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>私はエンタープライズ顧客です。 ローカル管理者は、デバイスの改ざん保護を変更できますか?

いいえ。 ローカル管理者は、改ざん防止設定を変更または変更できません。

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>デバイスがMicrosoft Defender for Endpointでオンボードされ、オフボード状態になった場合はどうなりますか?

デバイスがMicrosoft Defender for Endpointからオフボードされている場合は、改ざん防止が有効になります。これは非管理対象デバイスの既定の状態です。

### <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>改ざん防止の状態が変更された場合、Microsoft 365 Defender ポータルにアラートが表示されますか?

はい。 アラートは [アラート] に [https://security.microsoft.com](https://security.microsoft.com) 表示 **されます**。

セキュリティ運用チームは、次の例のようなハンティング クエリを使用することもできます。

`AlertInfo|where Title == "Tamper Protection bypass"`

[改ざんの試行に関する情報を表示します](#view-information-about-tampering-attempts)。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Endpoint Protection for Microsoft Intune を使用して Windows PC をセキュリティで保護する](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Defender for Endpoint の概要を確認する](/microsoft-365/security/defender-endpoint)
- [ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
- [トラブルシューティング モードを有効にする](enable-troubleshooting-mode.md)
- [トラブルシューティング モードがオンです](troubleshooting-mode-scenarios.md)
