---
title: Intuneを使用して USB デバイスやその他のリムーバブル メディアを制御する方法 (Windows 10)
description: INTUNE設定を構成して、USB デバイスなどのリムーバブル ストレージからの脅威を軽減できます。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.technology: mde
ROBOTS: NOINDEX
ms.openlocfilehash: 6ad51065ca4e919fe51cc4a2d5f4b0d53bc474b1
ms.sourcegitcommit: 1ef30b82d97bd998149235dc69d3c0e450e95285
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482492"
---
# <a name="how-to-control-usb-devices-and-other-removable-media-using-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Microsoft では[、リムーバブル メディアをセキュリティで保護するためのレイヤード アプローチ](https://aka.ms/devicecontrolblog)をお勧めします。Microsoft Defender for Endpointには、承認されていない周辺機器の脅威がデバイスを侵害するのを防ぐのに役立つ複数の監視機能と制御機能が用意されています。

1. [高度なハンティングで周辺機器のプラグ アンド プレイ接続イベントMicrosoft Defender for Endpoint検出](#discover-plug-and-play-connected-events)します。 疑わしい使用状況アクティビティを特定または調査します。

2. 特定のリムーバブル デバイスのみを許可またはブロックし、脅威を防止するように構成します。
    1. 詳細な構成に基づいて[リムーバブル デバイスを許可またはブロック](#allow-or-block-removable-devices)し、リムーバブル ディスクへの書き込みアクセスを拒否し、USB デバイス ID を使用してデバイスを承認または拒否します。 Azure Active Directory (Azure AD) ユーザーとデバイスの個々またはグループに基づいて、デバイスのインストール設定の柔軟なポリシー割り当て。

    2. [次を有効にして、リムーバブル ストレージ](#prevent-threats-from-removable-storage) デバイスによって導入されたリムーバブル ストレージからの脅威を防ぎます。
        - リムーバブル ストレージをスキャンしてマルウェアをスキャンするリアルタイム保護 (RTP) をMicrosoft Defender ウイルス対策します。
        - USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする攻撃面縮小 (ASR) USB 規則。
        - ユーザーがサインインするまで、Thunderbolt 用のカーネル DMA 保護や DMA のブロックなど、DMA 攻撃を軽減するためのダイレクト メモリ アクセス (DMA) 保護設定。

3. カスタム[検出ルール](/microsoft-365/security/defender-endpoint/custom-detection-rules)を使用して、これらのプラグ アンド プレイ イベントや他のMicrosoft Defender for Endpoint イベントに基づいてリムーバブル デバイスの使用状況を監視するための[カスタマイズされたアラートと応答アクションを作成](#create-customized-alerts-and-response-actions)します。

4. 各周辺機器によって報告されたプロパティに基づいて、リアルタイムで周辺機器からの[脅威に対応](#respond-to-threats)します。

> [!NOTE]
> これらの脅威軽減対策は、マルウェアが環境に侵入するのを防ぐのに役立ちます。 エンタープライズ データが環境から離れるのを防ぐには、データ損失防止対策を構成することもできます。 たとえば、Windows 10 デバイスでは[、BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) と[Windows Information Protection](/windows/security/information-protection/create-wip-policy-using-intune-azure.md)を構成できます。これは、個人のデバイスに保存されている場合でも会社のデータを暗号化したり、[Storage/RemovableDiskDenyWriteAccess CSP](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess) を使用してリムーバブル ディスクへの書き込みアクセスを拒否したりできます。 さらに、Microsoft Defender for Endpoint と Azure Information Protectionを使用して[、Windows デバイス](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview) (マウントされた USB デバイスを含む) 上のファイルを分類および保護できます。

## <a name="discover-plug-and-play-connected-events"></a>接続されたイベントのプラグ アンド プレイを検出する

プラグ アンド プレイ接続イベントは、高度な捜索Microsoft Defender for Endpoint表示して、不審な使用状況を特定したり、内部調査を実行したりできます。
Defender for Endpoint の高度なハンティング クエリの例については、[Microsoft Defender for Endpointの検索クエリGitHubリポジトリ](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)を参照してください。

高度な検索クエリに使用できるMicrosoft Defender for Endpointには、サンプル Power BI レポート テンプレートを使用できます。 デバイス制御用のテンプレートを含むこれらのサンプル テンプレートを使用すると、高度なハンティングの機能をPower BIに統合できます。 詳細については、[Power BI テンプレートのGitHub リポジトリ](https://github.com/microsoft/MDATP-PowerBI-Templates)を参照してください。 Power BI統合の詳細については、「[Power BIを使用してカスタム レポートを作成](/microsoft-365/security/defender-endpoint/api-power-bi)する」を参照してください。

## <a name="allow-or-block-removable-devices"></a>リムーバブル デバイスを許可またはブロックする
次の表では、詳細な構成に基づいてリムーバブル デバイスMicrosoft Defender for Endpoint許可またはブロックする方法について説明します。

<br>

****

|コントロール|説明|
|---|---|
|[USB ドライブとその他の周辺機器を制限する](#restrict-usb-drives-and-other-peripherals)|承認されたデバイスまたはデバイスの種類の一覧に含まれる USB ドライブとその他の周辺機器のみをインストールすることをユーザーに許可または禁止できます。|
|[リムーバブル ストレージのインストールと使用をブロックする](#block-installation-and-usage-of-removable-storage)|リムーバブル ストレージをインストールまたは使用することはできません。|
|[具体的に承認された周辺機器のインストールと使用を許可する](#allow-installation-and-usage-of-specifically-approved-peripherals)|ファームウェア内の特定のプロパティを報告する承認済みの周辺機器のみをインストールして使用できます。|
|[特に禁止されている周辺機器のインストールを禁止する](#prevent-installation-of-specifically-prohibited-peripherals)|ファームウェア内の特定のプロパティを報告する、禁止されている周辺機器をインストールまたは使用することはできません。|
|[一致するデバイス インスタンス ID を使用して、具体的に承認された周辺機器のインストールと使用を許可する](#allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids)|これらのデバイス インスタンス ID のいずれかに一致する承認済みの周辺機器のみをインストールして使用できます。|
|[一致するデバイス インスタンス ID を使用して、特に禁止されている周辺機器のインストールと使用を禁止する](#prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids)|これらのデバイス インスタンス ID のいずれかに一致する、禁止されている周辺機器をインストールまたは使用することはできません。|
|[Bluetoothを使用するサービスを制限する](#limit-services-that-use-bluetooth)|Bluetoothを使用できるサービスを制限できます。|
|

### <a name="restrict-usb-drives-and-other-peripherals"></a>USB ドライブとその他の周辺機器を制限する

マルウェアの感染やデータ損失を防ぐために、組織は USB ドライブやその他の周辺機器を制限する場合があります。 次の表では、USB ドライブやその他の周辺機器のインストールと使用を防ぐMicrosoft Defender for Endpoint方法について説明します。

<br>

****

|コントロール|説明
|---|---|
|[USB ドライブとその他の周辺機器のインストールと使用を許可する](#allow-installation-and-usage-of-usb-drives-and-other-peripherals)|承認されたデバイスまたはデバイスの種類の一覧に含まれる USB ドライブとその他の周辺機器のみをインストールできるようにする|
|[USB ドライブとその他の周辺機器のインストールと使用を禁止する](#prevent-installation-and-usage-of-usb-drives-and-other-peripherals)|承認されていないデバイスとデバイスの種類の一覧に含まれる USB ドライブやその他の周辺機器をユーザーがインストールできないようにする|
|

上記のすべてのコントロールは、Intune[管理用テンプレート](/intune/administrative-templates-windows)を使用して設定できます。 関連するポリシーは、Intune管理者テンプレートにあります。

![管理テンプレートの一覧のスクリーンショット。](images/admintemplates.png)

> [!NOTE]
> Intuneを使用すると、デバイス構成ポリシーをAzure ADユーザーまたはデバイス グループに適用できます。
上記のポリシーは、 [デバイス インストール CSP 設定とデバイス インストール](/windows/client-management/mdm/policy-csp-deviceinstallation) [GPO を](/previous-versions/dotnet/articles/bb530324(v=msdn.10))使用して設定することもできます。
>
> 運用環境に適用する前に、まずユーザーとデバイスのパイロット グループでこれらの設定をテストし、調整してください。
USB デバイスの制御の詳細については、[Microsoft Defender for Endpointブログ](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)を参照してください。

#### <a name="allow-installation-and-usage-of-usb-drives-and-other-peripherals"></a>USB ドライブとその他の周辺機器のインストールと使用を許可する

USB ドライブやその他の周辺機器のインストールと使用を許可する方法の 1 つは、すべてを許可することから始める方法です。 その後、許容される USB ドライバーとその他の周辺機器の削減を開始できます。

> [!NOTE]
> 未承認の USB 周辺機器には、USB プロパティを偽装するファームウェアが含まれる可能性があるため、特に承認された USB 周辺機器のみを許可し、アクセスできるユーザーを制限することをお勧めします。

1. [ **すべてのユーザーに対して他のポリシー設定で説明されていないデバイスのインストールを禁止** する] を有効にします。
2. [すべての **デバイス セットアップ クラスに対して、これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可** する] を有効にします。[](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)

既にインストールされているデバイスにポリシーを適用するには、この設定を持つ禁止ポリシーを適用します。

デバイスのインストールを許可するポリシーを構成する場合は、すべての親属性も許可する必要があります。 デバイスの親を表示するには、デバイス マネージャーを開き、接続で表示します。

![接続別のデバイス。](images/devicesbyconnection.png)

この例では、HID、キーボード、{36fc9e60-c465-11cf-8056-444553540000} のクラスを追加する必要があります。 詳細については、 [Microsoft 提供の USB ドライバー](/windows-hardware/drivers/usbcon/supported-usb-classes) を参照してください。

![デバイス ホスト コントローラー。](images/devicehostcontroller.jpg)

特定のデバイスに制限する場合は、制限する周辺機器のデバイス セットアップ クラスを削除します。 次に、追加するデバイス ID を追加します。 デバイス ID は、デバイスのベンダー ID と製品 ID の値に基づいています。 デバイス ID の形式については、「 [Standard USB 識別子」を](/windows-hardware/drivers/install/standard-usb-identifiers)参照してください。

デバイス ID を見つけるには、「 [デバイス ID の検索](#look-up-device-id)」を参照してください。

例:

1. **これらのデバイスのセットアップに一致するドライバーを使用してデバイスのインストールを許可する** から、クラス USBDevice を削除します。
2. これらのデバイス ID **のいずれかに一致するデバイスのインストールを許可するで許可するデバイス ID を追加します**。

#### <a name="prevent-installation-and-usage-of-usb-drives-and-other-peripherals"></a>USB ドライブとその他の周辺機器のインストールと使用を禁止する

デバイス クラスまたは特定のデバイスのインストールを禁止する場合は、デバイスのインストールを禁止するポリシーを使用できます。

1. [ **これらのデバイス ID のいずれかに一致するデバイスのインストールを禁止** する] を有効にして、これらのデバイスを一覧に追加します。
2. **これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを禁止する** を有効にします。

> [!NOTE]
> デバイスのインストールを禁止するポリシーは、デバイスのインストールを許可するポリシーよりも優先されます。

**[これらのデバイス ID のいずれかに一致するデバイスのインストールを禁止** する] ポリシーでは、Windowsがインストールできないデバイスの一覧を指定できます。

これらのデバイス ID のいずれかに一致するデバイスのインストールを防止するには、次の手順に従います。

1. インストールできないようにWindowsするデバイスの[デバイス ID を検索](#look-up-device-id)します。

   ![ベンダーまたは製品 ID を検索します。](images/lookup-vendor-product-id.png)

2. **[これらのデバイス ID のいずれかに一致するデバイスのインストールを禁止** する] を有効にし、ベンダーまたは製品の ID を一覧に追加します。

    ![リストを禁止するベンダー ID を追加します。](images/add-vendor-id-to-prevent-list.png)

#### <a name="look-up-device-id"></a>デバイス ID を検索する

デバイス マネージャーを使用して、デバイス ID を検索できます。

1. デバイス マネージャーを開きます。
2. [ **表示** ] をクリックし、[ **接続別のデバイス**] を選択します。
3. ツリーからデバイスを右クリックし、[ **プロパティ**] を選択します。
4. 選択したデバイスのダイアログ ボックスで、[ **詳細** ] タブをクリックします。
5. **[プロパティ**] ドロップダウン リストをクリックし、[**ハードウェア ID**] を選択します。
6. 上部の ID 値を右クリックし、[ **コピー**] を選択します。

デバイス ID 形式の詳細については、「 [Standard USB 識別子」を](/windows-hardware/drivers/install/standard-usb-identifiers)参照してください。

ベンダー ID については、 [USB メンバー](https://www.usb.org/members)を参照してください。

PowerShell を使用してデバイス ベンダー ID または製品 ID (デバイス ID の一部) を検索する例を次に示します。

```powershell
Get-WMIObject -Class Win32_DiskDrive | Select-Object -Property *
```

**[これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスをインストールできないようにする]** ポリシーでは、Windowsインストールできないデバイス セットアップ クラスを指定できます。

デバイスの特定のクラスのインストールを防止するには、次の手順を実行します。

1. [ベンダーが使用できるシステム定義デバイス セットアップ クラスから、デバイス セットアップ クラスの GUID を](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)見つけます。

2. **これらのデバイス セットアップ クラスと一致するドライバーを使用してデバイスのインストールを禁止** するを有効にし、クラス GUID を一覧に追加します。

    > [!div class="mx-imgBorder"]
    > ![リストを禁止するデバイス セットアップ クラスを追加します。](images/Add-device-setup-class-to-prevent-list.png)

### <a name="block-installation-and-usage-of-removable-storage"></a>リムーバブル ストレージのインストールと使用をブロックする

1. Microsoft エンドポイント マネージャー管理センター

2. [**デバイス** \> **構成プロファイルの作成] プロファイルを**\>クリック **します**。

    > [!div class="mx-imgBorder"]
    > ![デバイス構成プロファイルを作成します。](images/create-device-configuration-profile.png)

3. 次に示す設定を使用します。
   - 名前: プロファイルの名前を入力します
   - 説明: 説明を入力します
   - プラットフォーム: Windows 10 以降
   - プロファイルの種類: デバイスの制限

   > [!div class="mx-imgBorder"]
   > ![プロファイルを作成します。](images/create-profile.png)

4. [**全般****の構成] をクリックします**\>。

5. **リムーバブル ストレージ** と **USB 接続 (モバイルのみ)** の場合は、[**ブロック**] を選択します。 **リムーバブル ストレージ** には USB ドライブが含まれますが、 **USB 接続 (モバイルのみ)** では USB 充電は除外されますが、モバイル デバイス上のその他の USB 接続のみが含まれます。

   ![全般設定。](images/general-settings.png)

6. [ **OK] を** クリックして **、[全般** 設定] と [ **デバイスの制限]** を閉じます。

7. [ **作成** ] をクリックしてプロファイルを保存します。

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals"></a>具体的に承認された周辺機器のインストールと使用を許可する

インストールが許可されている周辺機器は、 [ハードウェア ID](/windows-hardware/drivers/install/device-identification-strings) で指定できます。 一般的な識別子構造の一覧については、「 [デバイス識別子の形式](/windows-hardware/drivers/install/device-identifier-formats)」を参照してください。 展開する前に構成をテストして、デバイスがブロックされ、必要なデバイスが許可されていることを確認します。 ハードウェアのさまざまなインスタンスをテストするのが理想的です。 たとえば、1 つのみではなく、複数の USB キーをテストします。

特定のデバイス ID のインストールを許可する SyncML の例については、「 [DeviceInstallation/AllowInstallationOfMatchingDeviceIDs CSP](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids)」を参照してください。 特定のデバイス クラスを許可するには、「 [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses CSP](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses)」を参照してください。
特定のデバイスのインストールを許可するには、 [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings も](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings)有効にする必要があります。

### <a name="prevent-installation-of-specifically-prohibited-peripherals"></a>特に禁止されている周辺機器のインストールを禁止する

Microsoft Defender for Endpointは、次のいずれかのオプションを使用して、禁止されている周辺機器のインストールと使用をブロックします。

- [管理用テンプレート](/intune/administrative-templates-windows) は、一致するハードウェア ID またはセットアップ クラスを持つ任意のデバイスをブロックできます。
- Intuneにカスタム プロファイルを含む[デバイス インストール CSP の設定](/windows/client-management/mdm/policy-csp-deviceinstallation)。 [特定のデバイス ID のインストールを禁止したり、特定の](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids)[デバイス クラスを防止したりできます](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses)。

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids"></a>一致するデバイス インスタンス ID を使用して、具体的に承認された周辺機器のインストールと使用を許可する

インストールが許可されている周辺機器は、 [デバイス インスタンス ID](/windows-hardware/drivers/install/device-instance-ids) で指定できます。 展開する前に構成をテストし、必要なデバイスが許可されていることを確認します。 ハードウェアのさまざまなインスタンスをテストするのが理想的です。 たとえば、1 つのみではなく、複数の USB キーをテストします。

[DeviceInstallation/AllowInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids) ポリシー設定を構成することで、デバイス インスタンス ID に一致する承認済み周辺機器のインストールと使用を許可できます。

### <a name="prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids"></a>一致するデバイス インスタンス ID を使用して、特に禁止されている周辺機器のインストールと使用を禁止する

インストールが禁止されている周辺機器は、 [デバイス インスタンス ID](/windows-hardware/drivers/install/device-instance-ids) で指定できます。 展開する前に構成をテストし、必要なデバイスが許可されていることを確認します。 ハードウェアのさまざまなインスタンスをテストするのが理想的です。 たとえば、1 つのみではなく、複数の USB キーをテストします。

[DeviceInstallation/PreventInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids) ポリシー設定を構成することで、一致するデバイス インスタンス ID で禁止されている周辺機器のインストールを防ぐことができます。

### <a name="limit-services-that-use-bluetooth"></a>Bluetoothを使用するサービスを制限する

Intuneを使用すると、["Bluetooth許可されたサービス"](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) を通じてBluetoothを使用できるサービスを制限できます。 "Bluetooth許可されたサービス" 設定の既定の状態は、すべてが許可されていることを意味します。  サービスが追加されるとすぐに、許可されたリストになります。 お客様がキーボードとマウスの値を追加し、ファイル転送 GUID を追加しない場合は、ファイル転送をブロックする必要があります。

> [!div class="mx-imgBorder"]
> ![Bluetooth設定ページのスクリーンショット。](images/bluetooth.png)

## <a name="prevent-threats-from-removable-storage"></a>リムーバブル ストレージからの脅威を防ぐ

リムーバブル ストレージ デバイスは、組織に追加のセキュリティ リスクを生じる可能性があります。 Microsoft Defender for Endpointは、リムーバブル ストレージ デバイス上の悪意のあるファイルを特定してブロックするのに役立ちます。

Microsoft Defender for Endpointでは、外部の脅威を防ぐために USB 周辺機器がデバイスで使用されないようにすることもできます。 これを行うには、USB 周辺機器によって報告されたプロパティを使用して、デバイスにインストールして使用できるかどうかを判断します。

デバイス インストール ポリシーを使用して USB デバイスまたはその他のデバイス クラスをブロックした場合でも、電話などの接続されたデバイスは引き続き課金される可能性があることに注意してください。

> [!NOTE]
> 組織に広く配布する前に、最初にユーザーとデバイスのパイロット グループでこれらの設定をテストし、調整してください。

次の表では、リムーバブル ストレージからの脅威を防ぐMicrosoft Defender for Endpoint方法について説明します。

USB デバイスの制御の詳細については、[Microsoft Defender for Endpointブログ](https://aka.ms/devicecontrolblog)を参照してください。

<br>

****

|コントロール|説明|
|---|---|
|[Microsoft Defender ウイルス対策スキャンを有効にする](#enable-microsoft-defender-antivirus-scanning)|リアルタイム保護またはスケジュールされたスキャンのMicrosoft Defender ウイルス対策スキャンを有効にします。|
|[USB 周辺機器で信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-on-usb-peripherals)|署名されていないか信頼されていない USB ファイルをブロックします。|
|[ダイレクト メモリ アクセス (DMA) 攻撃から保護する](#protect-against-direct-memory-access-dma-attacks)|DMA 攻撃から保護する設定を構成します。|
|

> [!NOTE]
> 未承認の USB 周辺機器には、USB プロパティを偽装するファームウェアが含まれる可能性があるため、特に承認された USB 周辺機器のみを許可し、アクセスできるユーザーを制限することをお勧めします。

### <a name="enable-microsoft-defender-antivirus-scanning"></a>Microsoft Defender ウイルス対策スキャンを有効にする

承認されたリムーバブル ストレージをMicrosoft Defender ウイルス対策で保護[するには、リアルタイムの保護](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)またはスキャンのスケジュール設定を有効にし、リムーバブル ドライブをスキャン用に構成する必要があります。

- リアルタイム保護が有効になっている場合は、ファイルにアクセスして実行する前にファイルがスキャンされます。 スキャン スコープには、USB ドライブなどのマウントされたリムーバブル デバイス上のファイルを含むすべてのファイルが含まれます。 必要に応じて [PowerShell スクリプトを実行して](/samples/browse/?redirectedfrom=TechNet-Gallery)、マウント後に USB ドライブのカスタム スキャンを実行Microsoft Defender ウイルス対策、リムーバブル デバイスがアタッチされると、リムーバブル デバイス上のすべてのファイルのスキャンを開始できます。 ただし、特に大規模なストレージ デバイスの場合は、スキャンパフォーマンスを向上させるためにリアルタイム保護を有効にすることをお勧めします。

- スケジュールされたスキャンを使用する場合は、DisableRemovableDriveScanning 設定 (既定で有効) を無効にして、完全スキャン中にリムーバブル デバイスをスキャンする必要があります。 リムーバブル デバイスは、DisableRemovableDriveScanning 設定に関係なく、クイック スキャンまたはカスタム スキャン中にスキャンされます。

> [!NOTE]
> スキャンのリアルタイム監視を有効にすることをお勧めします。 Intuneでは、**デバイス制限**\>の **構成** \> Microsoft Defender ウイルス対策リアルタイム監視でWindows 10 **のリアルタイム監視****を**\>有効にすることができます。

<!-- Need to build out point in the preceding note.
-->

### <a name="block-untrusted-and-unsigned-processes-on-usb-peripherals"></a>USB 周辺機器で信頼されていないプロセスと署名されていないプロセスをブロックする

エンド ユーザーは、マルウェアに感染しているリムーバブル デバイスを接続する可能性があります。
感染を防ぐために、会社は署名されていない、または信頼されていない USB ファイルをブロックできます。
また、企業は [、攻撃表面縮小ルール](/microsoft-365/security/defender-endpoint/attack-surface-reduction) の監査機能を利用して、USB 周辺機器で実行される信頼されていないプロセスと署名されていないプロセスのアクティビティを監視することもできます。
これは、 **USB から実行される信頼されていないプロセスと署名されていないプロセス** をそれぞれ **ブロック** または **監査のみに** 設定することによって行うことができます。
この規則を使用すると、管理者は、署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルが、SD カードを含む USB リムーバブル ドライブから実行されるのを防止または監査できます。
影響を受けるファイルの種類には、実行可能ファイル (.exe、.dll、.scr など) や、PowerShell (.ps)、VisualBasic (.vbs)、JavaScript (.js) ファイルなどのスクリプト ファイルが含まれます。

これらの設定では、 [リアルタイム保護を有効にする必要があります](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)。

1. Microsoft エンドポイント マネージャーにサインイン[します](https://endpoint.microsoft.com/)。

2. [**デバイス** \> **Windows** \> **構成ポリシー** \> **の作成プロファイル**] をクリックします。

    ![デバイス構成プロファイルを作成します。](images/create-device-configuration-profile.png)

3. 次に示す設定を使用します。
   - プラットフォーム: Windows 10 以降
   - プロファイルの種類: デバイスの制限

   > [!div class="mx-imgBorder"]
   > ![エンドポイント保護プロファイルを作成します。](images/create-endpoint-protection-profile.png)

4. **[作成]** をクリックします。

5. **USB から実行される署名されていないプロセスと信頼されていないプロセスの場合は**、[ブロック] を選択 **します**。

   ![信頼されていないプロセスをブロックします。](images/block-untrusted-processes.png)

6. [ **OK] を** クリックして設定と **デバイスの制限を** 閉じます。

### <a name="protect-against-direct-memory-access-dma-attacks"></a>ダイレクト メモリ アクセス (DMA) 攻撃から保護する

DMA 攻撃は、PC 上に存在する機密情報の開示や、攻撃者がロック画面をバイパスしたり、PC をリモートで制御したりできるマルウェアの挿入につながる可能性があります。 次の設定は、DMA 攻撃を防ぐのに役立ちます。

1. Microsoft では、Windows 10 バージョン 1803 以降、[Thunderbolt のカーネル DMA 保護](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md)を導入し、Thunderbolt ポートを介した DMA 攻撃に対するネイティブ保護を提供しました。 Thunderbolt 用のカーネル DMA 保護はシステム製造元によって有効になっており、ユーザーがオンまたはオフにすることはできません。

   Windows 10 バージョン 1809 以降では、[DMA Guard CSP](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy) を構成することで、カーネル DMA 保護のレベルを調整できます。 これは、デバイス メモリの分離 (DMA 再マッピングとも呼ばれます) をサポートしない周辺機器の追加コントロールです。 メモリ分離を使用すると、OS はデバイスの I/O メモリ管理ユニット (IOMMU) を利用して、周辺機器 (メモリ サンドボックス) による未承認の I/O またはメモリ アクセスをブロックできます。 つまり、OS は周辺機器に特定のメモリ範囲を割り当てます。 周辺機器が割り当てられた範囲外のメモリへの読み取り/書き込みを試みると、OS によってブロックされます。

   デバイスメモリの分離をサポートする周辺機器は、常に接続できます。 ユーザーがサインインした後にのみブロック、許可、または許可できない周辺機器 (既定値)。

2. カーネル DMA 保護をサポートしていないWindows 10 システムでは、次のことができます。

   - [ユーザーがサインインするまで DMA をブロックする](/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)
   - [Thunderbolt ポート (USB デバイスを含む) 経由ですべての接続をブロックする](https://support.microsoft.com/help/2516445/blocking-the-sbp-2-driver-and-thunderbolt-controllers-to-reduce-1394-d)

## <a name="create-customized-alerts-and-response-actions"></a>カスタマイズされたアラートと応答アクションを作成する

WDATP コネクタとカスタム検出ルールを使用して、カスタム アラートと応答アクションを作成できます。

**Wdatp コネクタ応答アクション:**

**調査：** 調査を開始し、調査パッケージを収集し、コンピューターを分離します。

USB デバイス **での脅威スキャン**。

定義済みのセットを除くマシン上 **のすべてのアプリケーションの実行を制限** する

MDATP コネクタは、Outlook、Teams、Slack など、200 以上の定義済みコネクタの 1 つです。カスタム コネクタを構築できます。

- [WDATP コネクタ応答アクションの詳細](/connectors/wdatp/)

**カスタム検出ルールの応答アクション:**

コンピューター レベルとファイル レベルの両方のアクションを適用できます。

- [カスタム検出ルールの応答アクションの詳細](/microsoft-365/security/defender-endpoint/custom-detection-rules)

デバイス制御関連の事前捜索イベントとカスタム アラートを作成する方法の例については、「 [高度なハンティング更新プログラム:USB イベント、マシン レベルのアクション、およびスキーマの変更](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152)」を参照してください。

## <a name="respond-to-threats"></a>脅威に対応する

[Microsoft Defender for Endpointカスタム検出ルール](/microsoft-365/security/defender-endpoint/custom-detection-rules)を使用して、カスタム アラートと自動応答アクションを作成できます。 カスタム検出内の応答アクションは、マシン レベルとファイル レベルの両方のアクションに対応します。 Microsoft Defender for Endpoint [コネクタ](/connectors/wdatp/)で[Power Apps](https://powerapps.microsoft.com/)と[Flow](https://flow.microsoft.com/)を使用して、アラートと自動応答アクションを作成することもできます。 コネクタは、アプリケーションの調査、脅威スキャン、および実行を制限するためのアクションをサポートします。 Outlook、Teams、Slack など、200 を超える定義済みのコネクタの 1 つです。 カスタム コネクタを構築することもできます。 [コネクタの](/connectors/)詳細については、「コネクタ」を参照してください。

たとえば、どちらの方法を使用しても、USB デバイスがコンピューターにマウントされたときにMicrosoft Defender ウイルス対策を自動的に実行できます。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策のリアルタイム保護を構成する](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
- [Defender/AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)
- [Policy/DeviceInstallation CSP](/windows/client-management/mdm/policy-csp-deviceinstallation)
- [リムーバブル デバイスのカスタム スキャンを実行する](/samples/browse/?redirectedfrom=TechNet-Gallery)
- [カスタム レポート用の Device Control Power BI テンプレート](https://github.com/microsoft/MDATP-PowerBI-Templates)
- [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md)
- [Windows 情報保護](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure.md)
