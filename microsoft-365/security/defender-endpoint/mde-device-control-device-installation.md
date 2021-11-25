---
title: Microsoft Defender for Endpoint Device Control Device Installation
description: このトピックでは、Microsoft Defender for Endpoint Device Control Device Installation について説明します。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f0828d24ddb4c02d533d0fced2389ca3cb61ce4
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167072"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Microsoft Defender for Endpoint Device Control Device Installation 

**適用対象**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint Device Control リムーバブル Storageアクセス制御を使用すると、次のタスクを実行できます。

- ユーザーが特定のデバイスをインストールするのを防ぐ。
- ユーザーが特定のデバイスをインストールできますが、他のデバイスをインストールできません。

> [!NOTE]
> デバイス インストールとリムーバブル 記憶域アクセス制御の違いについては、「Microsoft Defender for Endpoint Device Control Removable Storage [Protection」を参照してください](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true)。

|特権|アクセス許可|
|---|---|
|Access|デバイスのインストール |
|アクション モード|許可、防止 |
|CSP サポート|はい|
|GPO サポート|はい|
|ユーザー ベースのサポート|いいえ|
|コンピューター ベースのサポート|はい|

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

サーバー 2022 Windows 10、Windows 11 台のデバイスWindows展開します。

## <a name="device-properties"></a>デバイス プロパティ

デバイス インストール のサポートでは、次のデバイス プロパティがサポートされています。

- デバイス ID 
- ハードウェア ID 
- 互換性のある ID 
- デバイス クラス 
- 'リムーバブル デバイス' デバイスの種類: 一部のデバイスは、リムーバブル デバイスとして分類できます。 デバイスが接続されているデバイスのドライバーが、デバイスがリムーバブルであると示されている場合、デバイスはリムーバブルと見なされます。 たとえば、USB デバイスは、デバイスが接続されている USB ハブのドライバーによってリムーバブルと報告されます。 詳細については、「デバイス の[インストール」を参照Windows。](/windows/client-management/manage-device-installation-with-group-policy)

## <a name="policies"></a>ポリシー

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>これらのデバイスの ID に一致するデバイスのインストールを許可する

このポリシー設定では、プラグ アンド プレイ ハードウェアの一覧と、インストールが許可されているデバイスWindows互換性のある ID を指定できます。 このポリシー設定は、[すべてのデバイスの一致条件に対してデバイスのインストール ポリシーを許可する] ポリシーと [デバイスのインストールを防止する] の評価の順序を適用するポリシー設定が有効になっている場合にのみ使用されます。

このポリシー設定が [すべてのデバイスの一致条件ポリシーに対してデバイスインストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定と共に有効になっている場合、階層内の同じ層以上の別のポリシー設定でインストールを特に妨げる場合を含め、Windows は、作成したリストにプラグ アンド プレイ ハードウェア ID または互換性のある ID が表示されるデバイスをインストールまたは更新できます。 次のポリシー設定など。

- これらのデバイスの ID に一致するデバイスのインストールを防止します。
- これらのデバイス インスタンスの ID に一致するデバイスのインストールを防止します。

[すべてのデバイスの一致条件ポリシーに対してデバイスのインストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定がこのポリシー設定で有効になっていない場合は、インストールを特に防止する他のポリシー設定が優先されます。 

> [!NOTE]
> [**他** のポリシー設定で説明されていないデバイスのインストールを防止する] ポリシー設定は、サポートされているターゲット Windows 10 バージョンおよび Windows 11 のすべてのデバイス一致条件ポリシー設定で[デバイスのインストール ポリシーを許可および防止する] の評価のレイヤー順に置き換えられます。 可能な場合は、[許可] ポリシーと [デバイスインストール ポリシーをすべてのデバイス一致条件に適用する] ポリシー設定に対して、層別の評価順序 **を適用する** を使用してください。

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>これらのデバイス インスタンスの ID に一致するデバイスのインストールを許可する 

このポリシー設定では、インストールが許可されているデバイスのプラグ アンド プレイ デバイス インスタンスの一Windows指定できます。 このポリシー設定は、[すべてのデバイスの一致条件に対してデバイスのインストール ポリシーを許可する] ポリシーと [デバイスのインストールを防止する] の評価の順序を適用するポリシー設定が有効になっている場合にのみ使用されます。 

このポリシー設定が [すべてのデバイスの一致条件ポリシーに対してデバイスのインストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定と共に有効になっている場合、階層内の同じ層以上の別のポリシー設定がインストールを特に妨げる場合を含め、Windows は、作成したリストにプラグ アンド プレイ デバイス インスタンス ID が表示されるデバイスをインストールまたは更新できます。 次のポリシー設定など。

- これらのデバイス インスタンスの ID に一致するデバイスのインストールを防止する 

[すべてのデバイスの一致条件ポリシーに対してデバイスのインストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定がこのポリシー設定で有効になっていない場合は、インストールを特に防止する他のポリシー設定が優先されます。 

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可する 

このポリシー設定では、インストールが許可されているドライバー パッケージのデバイス セットアップ クラスのグローバル一意識別子 (GUID) のWindows指定できます。 このポリシー設定は、[すべてのデバイスの一致条件に対してデバイスのインストール ポリシーを許可する] ポリシーと [デバイスのインストールを防止する] の評価の順序を適用するポリシー設定が有効になっている場合にのみ使用されます。

このポリシー設定が [すべてのデバイスの一致条件ポリシーに対してデバイス インストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定と共に有効になっている場合、Windows は、デバイス セットアップ クラスの GUID が作成したリストに表示されるドライバー パッケージをインストールまたは更新できます。階層内の同じ層以上の層にある別のポリシー設定が、そのインストールを特に妨げる場合を含む限り、Windows はドライバー パッケージをインストールまたは更新できます。 次のポリシー設定など。 

- これらのデバイス クラスのデバイスのインストールを防止する 
- これらのデバイスの ID に一致するデバイスのインストールを防止する 
- これらのデバイス インスタンスの ID に一致するデバイスのインストールを防止する 

[すべてのデバイスの一致条件ポリシーに対してデバイスのインストール ポリシーを許可および防止する] の評価順序を適用するポリシー設定がこのポリシー設定で有効になっていない場合は、インストールを特に防止する他のポリシー設定が優先されます。

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>すべてのデバイスの一致条件に対して、デバイスのインストール ポリシーの許可と防止に対する評価の層順を適用する 

このポリシー設定は、特定のデバイスに複数のインストール ポリシー設定が適用される場合にポリシー設定を許可および防止する評価順序を変更します。 このポリシー設定を有効にすると、重複するデバイスの一致条件が確立された階層に基づいて適用され、より具体的な一致条件は、より特定の一致条件よりも置きかかっています。 デバイスの一致条件を指定するポリシー設定の評価の階層的な順序は次のとおりです。

**デバイス インスタンスの ID >デバイスのセットアップ >リムーバブル デバイス>デバイスのセットアップ クラス**

#### <a name="device-instance-ids"></a>デバイス インスタンスの ID 

1. これらのデバイス インスタンスの ID に一致するドライバーを使用してデバイスのインストールを防止します。
2. これらのデバイス インスタンスの ID に一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="device-ids"></a>デバイス ID 

1. これらのデバイスの ID に一致するドライバーを使用してデバイスのインストールを防止します。
2. これらのデバイスの ID に一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="device-setup-class"></a>デバイス セットアップ クラス 

1. これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを防止します。
2. これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="removable-devices"></a>リムーバブル デバイス 

リムーバブル デバイスのインストールを防止する 

> [!NOTE]
> このポリシー設定は、[他のポリシー設定で説明されていないデバイスのインストールを防止する] ポリシー設定よりも **詳細な制御を** 提供します。 これらの競合するポリシー設定が同時に有効になっている場合、[すべてのデバイスの一致条件に対してデバイスのインストール ポリシーを許可する] ポリシーと [デバイスインストール ポリシーを無効にする] の評価順序を適用するポリシー設定は有効になります。その他のポリシー設定は無視されます。 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>これらのデバイスの ID に一致するデバイスのインストールを防止する 

このポリシー設定では、プラグ アンド プレイ ハードウェアの一覧と、インストールが妨Windowsデバイスの互換性のある ID を指定できます。 既定では、このポリシー設定は、デバイスのインストールを許可する他Windowsよりも優先されます。

> [!NOTE]
> [これらのデバイス インスタンス **の IDs** ポリシーに一致するデバイスのインストールを許可する] ポリシー設定を有効にして、該当するデバイスに対してこのポリシー設定を変更するには、[すべてのデバイスの一致条件ポリシーでデバイスのインストール ポリシーを許可および防止する] の評価のレイヤー順を適用するポリシー設定 **を有効にします** 。 

このポリシー設定を有効にすると、Windowsリストにハードウェア ID または互換性のある ID が表示されるデバイスがインストールされません。 リモート デスクトップ サーバーでこのポリシー設定を有効にすると、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定したデバイスのリダイレクトに影響します。

このポリシー設定を無効にした場合、または構成しない場合は、他のポリシー設定で許可または防止されたデバイスをインストールおよび更新できます。 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>これらのデバイス インスタンスの ID に一致するデバイスのインストールを防止する 

このポリシー設定を使用すると、インストールが妨Windowsデバイスのプラグ アンド プレイ デバイス インスタンスの一覧を指定できます。 このポリシー設定は、デバイスのインストールを許可する他のWindowsよりも優先されます。 

このポリシー設定を有効にすると、Windowsリストにデバイス インスタンス ID が表示されるデバイスがインストールされません。 リモート デスクトップ サーバーでこのポリシー設定を有効にすると、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定したデバイスのリダイレクトに影響します。 

このポリシー設定を無効にした場合、または構成しない場合は、他のポリシー設定で許可または防止されたデバイスをインストールおよび更新できます。 

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを防止する 

このポリシー設定では、デバイス セットアップ クラスの一覧を、インストールが妨Windowsドライバー パッケージのグローバル一意識別子 (GUID) を指定できます。 既定では、このポリシー設定は、デバイスのインストールを許可する他Windowsよりも優先されます。

> [!NOTE]
> [これらのデバイス **の ID** に一致するデバイスのインストールを許可する] と [これらのデバイス インスタンス **の IDs** ポリシー設定に一致するデバイスのインストールを許可する] を有効にして、該当するデバイスに対してこのポリシー設定を超える場合は、[すべてのデバイスの一致条件ポリシーでデバイスのインストール ポリシーを許可および防止する] の評価のレイヤー順を適用するポリシー設定 **を有効にします** 。

このポリシー設定を有効にすると、Windowsリストにデバイス セットアップ クラス GUID が表示されるドライバー パッケージをインストールまたは更新する機能が無効になります。 リモート デスクトップ サーバーでこのポリシー設定を有効にすると、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定したデバイスのリダイレクトに影響します。 

このポリシー設定を無効にした場合、または構成しない場合は、Windows設定で許可または防止されているデバイスをインストールおよび更新できます。 

### <a name="prevent-installation-of-removable-devices"></a>リムーバブル デバイスのインストールを防止する 

このポリシー設定を使用すると、リムーバブル デバイスWindowsのインストールを防止できます。 デバイスが接続されているデバイスのドライバーが、デバイスがリムーバブルであると示されている場合、デバイスはリムーバブルと見なされます。 たとえば、ユニバーサル シリアル バス (USB) デバイスは、デバイスが接続されている USB ハブのドライバーによって取り外し可能と報告されます。 既定では、このポリシー設定は、デバイスのインストールを許可する他Windowsよりも優先されます。 

> [!NOTE]
> これらのデバイスセットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可する、これらのデバイスの ID と一致するデバイスのインストールを許可する、およびこれらのデバイス インスタンス **の IDs** ポリシー設定に一致するデバイスのインストールを許可して、該当するデバイスに対してこのポリシー設定を超える場合は、[すべてのデバイス一致条件ポリシーでデバイスのインストール ポリシーを許可および防止する] の評価のレイヤー順を適用するポリシー設定を有効にします。

このポリシー設定を有効にすると、Windowsデバイスのインストールが妨がり、既存のリムーバブル デバイスはドライバーを更新できません。 リモート デスクトップ サーバーでこのポリシー設定を有効にすると、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへのリムーバブル デバイスのリダイレクトに影響します。

このポリシー設定を無効にするか構成しない場合、Windowsは、他のポリシー設定で許可または防止されているリムーバブル デバイスのドライバー パッケージをインストールおよび更新できます。

## <a name="common-removable-storage-access-control-scenarios"></a>一般的なリムーバブル Storage アクセス制御のシナリオ

Microsoft Defender for Endpoint Removable Storageアクセス制御について理解するために、一般的なシナリオをまとめました。

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>シナリオ 1: 承認された USB サム ドライブのインストールのみを許可しながら、すべての USB デバイスのインストールを防止する 

このシナリオでは、次のポリシーが使用されます。

- これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを防止します。
- すべてのデバイスの一致条件に対して、デバイスのインストール ポリシーを許可および防止するに対して、評価の層順を適用します。
- これらのデバイス インスタンスの ID に一致するデバイスのインストールを許可するか、またはこれらのデバイスの ID に一致するデバイスのインストールを許可します。

#### <a name="deploying-and-managing-policy-via-intune"></a>Intune によるポリシーの展開と管理 

デバイスのインストール機能を使用すると、Intune を介してデバイスにポリシーを適用できます。

#### <a name="licensing"></a>ライセンス 

デバイスのインストールを開始する前に、サブスクリプションを確認Microsoft 365 [必要があります](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 デバイス のインストールにアクセスして使用するには、デバイスのインストールMicrosoft 365 E3。

#### <a name="permission"></a>アクセス許可 

Intune でのポリシー展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールを使用できます。  

- ポリシーとプロファイル マネージャーの役割
- または、デバイス構成プロファイルでレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール
- またはグローバル管理者

#### <a name="deploying-policy"></a>ポリシーの展開 

In Microsoft エンドポイント マネージャー [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)  

1. [構成 **] これらのデバイス セットアップ クラスに一致するドライバーを使用したデバイスのインストールを防止します**。

    - Open Endpoint security > 攻撃表面の縮小 > ポリシー > プラットフォームの作成: Windows 10 (以降) & プロファイル: デバイス制御。
    
      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="プロファイルの編集":::
    
2. USB デバイスをプラグインすると、次のエラー メッセージが表示されます。

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="エラー メッセージ":::

3. [すべてのデバイスの一致条件でデバイスのインストール ポリシーを許可する] と [デバイスのインストールを防止する] の評価のレイヤー順 **を適用するを有効にします**。

    - **今のところ OMA-URI** のみをサポートしています: デバイス > 構成プロファイル > プロファイル> プラットフォームの作成: Windows 10 (以降) & プロファイル: Custom
    
      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="行の編集":::

4. 許可されている USB インスタンス ID を有効にして追加する – これらのデバイス ID に一致するデバイスのインストール **を許可します**。

    - 手順 1 デバイス制御プロファイルを更新する
    
      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="devicecontrol":::
       
    PCI\CC_0C03の追加。PCI\CC_0C0330。PCI\VEN_8086。PNP0CA1;PNP0CA1 &HOST; USB\ROOT_HUB30;USB\ROOT_HUB20。画面キャプチャUSB20_HUB USB\USB20_HUB 1 つの USB サム ドライブを有効にするには、単一のハードウェア ID のみを有効にするのに十分ではないのでです。 ターゲットデバイスの前のすべての USB デバイスもブロック (許可) されない必要があります。 デバイス マネージャーを開き、PnP ツリーにデバイスをインストールする方法を確認するために、ビューを [接続別デバイス] に変更できます。 この場合、ターゲットの USB サム ドライブも許可される可能性がある場合は、次のデバイスを許可する必要があります。 

    - "Intel(R) USB 3.0 eXtensible ホスト コントローラー – 1.0 (Microsoft)" -> PCI\CC_0C03 
    - "USB ルート ハブ (USB 3.0)" -> USB\ROOT_HUB30 
    - "Generic USB Hub" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="デバイス制御":::

    > [!NOTE]
    > システム内の一部のデバイスには、システムへのインストールを定義する複数の接続層があります。 USB サム ドライブは、このようなデバイスです。 したがって、システムでそれらをブロックまたは許可する場合は、各デバイスの接続のパスを理解することが重要です。 システムで一般的に使用される一般的なデバイスの ID がいくつかあるので、このような場合に "許可リスト" を作成するための良いスタートを提供できます。 次に示す例は 1 つです (すべての USB では常に同じではありません。デバイス マネージャーを介して管理するデバイスの PnP ツリーを理解する必要があります)。
    >
    > PCI\CC_0C03;PCI\CC_0C0330。PCI\VEN_8086。PNP0CA1;PNP0CA1&HOST (ホスト コントローラー用)/USB\ROOT_HUB30。USB\ROOT_HUB20 (USB ルート ハブ用)/USB\USB20_HUB (汎用 USB ハブ用)/ 
    >
    > 特にデスクトップ コンピューターの場合は、キーボードとマウスが接続しているすべての USB デバイスを上記の一覧に記載することが重要です。 そうしない場合、ユーザーが HID デバイスを介してコンピューターにアクセスできません。 
    >
    > PC の製造元によって、PnP ツリーに USB デバイスを入れ子にする方法が異なる場合がありますが、一般的には、この方法を使用します。 

5. 許可されている USB を再度接続します。 これで、許可と利用可能が表示されます。

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="ドライブを削除する":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>グループ ポリシーによるポリシーの展開と管理

デバイスのインストール機能を使用すると、グループ ポリシーを使用してポリシーを適用できます。

#### <a name="licensing"></a>ライセンス

デバイス のインストールにアクセスして使用するには、E3 にアクセスWindows必要があります。

#### <a name="deploying-policy"></a>ポリシーの展開

展開の詳細については、グループ ポリシーを使用してデバイスインストールを管理[する (Windows 10) - Windowsします](/windows/client-management/manage-device-installation-with-group-policy)。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint Storageデバイス コントロールリムーバブル アクセス制御データを表示する

セキュリティ[Microsoft 365には、](https://sip.security.microsoft.com/homepage)デバイスコントロール デバイスのインストールによってブロックされたリムーバブル 記憶域が表示されます。 セキュリティにアクセスするにはMicrosoft 365サブスクリプションが必要です。

- Microsoft 365 E5 レポートの詳細

```kusto
//events triggered by Device Installation policies 
DeviceEvents 
| where ActionType == "PnpDeviceBlocked" or ActionType == "PnpDeviceAllowed" 
| extend parsed=parse_json(AdditionalFields) 
| extend MediaClassGuid = tostring(parsed.ClassGuid)  
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaDeviceId = tostring(parsed.MatchingDeviceId) 
| project Timestamp , DeviceId, DeviceName, ActionType, MediaClassGuid, MediaDeviceId, MediaInstanceId, AdditionalFields 
| order by Timestamp desc 
```

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="ブロック ストレージ":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>ターゲット コンピューターが展開されたポリシーを取得するかどうかを確認する方法 
次のクエリを使用して、セキュリティ ポータルでマルウェア対策クライアントのMicrosoft 365できます。

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens   
DeviceRegistryEvents 
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\" 
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>許可ポリシーが機能しない理由
単一の USB サム ドライブを有効にするには、1 つのハードウェア ID のみを有効にするのに十分ではありません。 ターゲットデバイスの前のすべての USB デバイスもブロック (許可) されていないか確認します。

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="デバイスのインストールに関するよく寄せられる質問":::

