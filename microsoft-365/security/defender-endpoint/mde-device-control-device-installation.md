---
title: Microsoft Defender for Endpoint デバイス制御デバイスのインストール
description: このトピックでは、デバイスコントロール デバイスのインストールMicrosoft Defender for Endpointについて説明します
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
ms.openlocfilehash: dc05633d1badfc29b2179915ac6d318dd9523834
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666396"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Microsoft Defender for Endpoint デバイス制御デバイスのインストール

**適用対象**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

デバイスコントロール デバイスのインストールMicrosoft Defender for Endpoint、次のタスクを実行できます。

- ユーザーが特定のデバイスをインストールできないようにします。
- ユーザーが特定のデバイスをインストールできるようにするが、他のデバイスを禁止する。

> [!NOTE]
> デバイスのインストールとリムーバブル ストレージのアクセス制御の違いについては、「[デバイスコントロールのリムーバブル Storage保護Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true)参照してください。

|特権|アクセス許可|
|---|---|
|Access|デバイスのインストール |
|アクション モード|許可、禁止 |
|CSP サポート|はい|
|GPO のサポート|はい|
|ユーザー ベースのサポート|不要|
|マシンベースのサポート|はい|

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

Windows 10、Windows 11 デバイス、Windows Server 2022 にデバイス インストールを展開します。

## <a name="device-properties"></a>デバイス プロパティ

デバイス インストールのサポートでは、次のデバイス プロパティがサポートされています。

- デバイス ID
- ハードウェア ID
- 互換性のある ID
- デバイス クラス
- "リムーバブル デバイス" デバイスの種類: 一部のデバイスはリムーバブル デバイスとして分類できます。 デバイスが接続されているデバイスのドライバーが、デバイスがリムーバブルであることを示す場合、デバイスはリムーバブルと見なされます。 たとえば、USB デバイスは、デバイスが接続されている USB ハブのドライバーによって取り外し可能であると報告されます。
詳細については、「[Windowsでのデバイスのインストール](/windows/client-management/manage-device-installation-with-group-policy)」を参照してください。

## <a name="policies"></a>ポリシー

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>これらのデバイス ID のいずれかに一致するデバイスのインストールを許可する

このポリシー設定を使用すると、インストールが許可されているデバイスのプラグ アンド プレイハードウェア ID と互換性のある ID の一覧Windows指定できます。 このポリシー設定は、 **すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止] デバイス インストール ポリシーの評価のレイヤー順を適用** する場合にのみ使用することを目的としています。

このポリシー設定が、**すべてのデバイス一致条件ポリシー設定に対するデバイスインストール ポリシーの許可と禁止の評価の階層化された順序** と共に有効になっている場合、階層内の同じ層以上の別のポリシー設定が特に禁止されていない限り、プラグ アンド プレイハードウェア ID または互換性 ID がリストに表示されるデバイスのインストールまたは更新が許可Windows 次のポリシー設定など、インストールします。

- これらのデバイス ID に一致するデバイスのインストールを禁止します。
- これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを禁止します。

**すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止デバイス インストール ポリシー] の評価の階層化順序を適用** するが、このポリシー設定で有効になっていない場合は、インストールを禁止するその他のポリシー設定が優先されます。

> [!NOTE]
> **[他のポリシー設定で説明されていないデバイスのインストールを禁止する]** ポリシー設定は、サポートされているターゲット Windows 10 のバージョン **とWindows 11に対するすべてのデバイス一致条件ポリシー設定で、デバイスのインストール ポリシーを許可および禁止するための階層化された評価順序の適用** に置き換えられました。 可能な場合は、 **すべてのデバイス一致条件ポリシー設定で、[許可] ポリシーと [禁止] デバイス インストール ポリシーに対してレイヤー化された評価順序を適用** することをお勧めします。

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを許可する

このポリシー設定を使用すると、インストールが許可されているデバイスのデバイス インスタンス ID プラグ アンド プレイWindows一覧を指定できます。 このポリシー設定は、 **すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止] デバイス インストール ポリシーの評価のレイヤー順を適用** する場合にのみ使用することを目的としています。

このポリシー設定が、**すべてのデバイス一致条件ポリシー設定に対するデバイスインストール ポリシーの許可と禁止の評価の階層化された順序** と共に有効になっている場合、階層内の同じ層以上の別のポリシー設定が特に禁止されていない限り、Windowsは、作成した一覧にプラグ アンド プレイデバイス インスタンス ID が表示されるすべてのデバイスのインストールまたは更新を許可されます。 次のポリシー設定など、インストールします。

- これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを禁止する

**すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止デバイス インストール ポリシー] の評価の階層化順序を適用** するが、このポリシー設定で有効になっていない場合は、インストールを禁止するその他のポリシー設定が優先されます。

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可する

このポリシー設定を使用すると、インストールが許可Windowsドライバー パッケージのデバイス セットアップ クラスグローバル一意識別子 (GUID) の一覧を指定できます。 このポリシー設定は、 **すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止] デバイス インストール ポリシーの評価のレイヤー順を適用** する場合にのみ使用することを目的としています。

このポリシー設定が、**すべてのデバイス一致条件ポリシー設定に対するデバイスインストール ポリシーの許可と禁止の評価の階層化された順序** と共に有効になっている場合、階層内の同じ層以上の別のポリシー設定で特にそのインストールが禁止されていない限り、デバイス セットアップ クラスの GUID が作成した一覧に表示されるドライバー パッケージをインストールまたは更新Windows許可されます。 次のポリシー設定などです。

- これらのデバイス クラスのデバイスのインストールを禁止する
- これらのデバイス ID に一致するデバイスのインストールを禁止する
- これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを禁止する

**すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止デバイス インストール ポリシー] の評価の階層化順序を適用** するが、このポリシー設定で有効になっていない場合は、インストールを禁止するその他のポリシー設定が優先されます。

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>すべてのデバイス一致条件に対して、デバイスのインストール ポリシーを許可および禁止するための階層化された評価順序を適用する

このポリシー設定は、特定のデバイスに複数のインストール ポリシー設定が適用されている場合に、ポリシー設定を許可および禁止する評価順序を変更します。 このポリシー設定を有効にすると、より具体的な一致条件がより具体的な一致条件よりも優先される、確立された階層に基づいて重複するデバイス一致条件が適用されます。 デバイス一致条件を指定するポリシー設定の評価の階層的な順序は次のとおりです。

**デバイス インスタンス ID** \>**デバイス ID** \>**デバイス セットアップ クラス** \>**リムーバブル デバイス**

#### <a name="device-instance-ids"></a>デバイス インスタンス ID

1. これらのデバイス インスタンス ID に一致するドライバーを使用してデバイスのインストールを禁止します。
2. これらのデバイス インスタンス ID に一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="device-ids"></a>デバイス ID

1. これらのデバイス ID に一致するドライバーを使用してデバイスのインストールを禁止します。
2. これらのデバイス ID に一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="device-setup-class"></a>デバイス セットアップ クラス

1. これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスをインストールできないようにします。
2. これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可します。

#### <a name="removable-devices"></a>リムーバブル デバイス

リムーバブル デバイスのインストールを禁止する

> [!NOTE]
> このポリシー設定は、[ **他のポリシー設定で説明されていないデバイスのインストールを禁止する]** ポリシー設定よりも詳細な制御を提供します。 これらの競合するポリシー設定が同時に有効になっている場合は、 **すべてのデバイス一致条件ポリシー設定で[許可] ポリシーと [禁止] デバイス インストール ポリシーの評価の階層化された順序を適用** するポリシー設定が有効になり、他のポリシー設定は無視されます。

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>これらのデバイス ID のいずれかに一致するデバイスのインストールを禁止する

このポリシー設定を使用すると、Windowsがインストールできないデバイスのプラグ アンド プレイハードウェア ID と互換性のある ID の一覧を指定できます。 既定では、このポリシー設定は、デバイスのインストールWindows許可する他のポリシー設定よりも優先されます。

> [!NOTE]
> **[これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを許可** する] ポリシー設定を有効にして、該当するデバイスに対してこのポリシー設定を置き換えるには、[**すべてのデバイス一致条件ポリシーでデバイスインストール ポリシーを許可および禁止する] ポリシー設定で、階層化された評価順序の適用** を有効にします。

このポリシー設定を有効にすると、作成した一覧にハードウェア ID または互換性 ID が表示されるデバイスのインストールがWindowsに禁止されます。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定はリモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。

このポリシー設定を無効にした場合、または構成していない場合は、他のポリシー設定で許可または禁止されているデバイスをインストールおよび更新できます。

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを禁止する

このポリシー設定を使用すると、Windowsがインストールできないデバイスのデバイス インスタンス ID プラグ アンド プレイ一覧を指定できます。 このポリシー設定は、デバイスのインストールWindows許可する他のポリシー設定よりも優先されます。

このポリシー設定を有効にすると、作成Windows一覧にデバイス インスタンス ID が表示されるデバイスをインストールできなくなります。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定はリモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。

このポリシー設定を無効にした場合、または構成していない場合は、他のポリシー設定で許可または禁止されているデバイスをインストールおよび更新できます。

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスをインストールできないようにする

このポリシー設定を使用すると、ドライバー パッケージのデバイス セットアップ クラスのグローバル一意識別子 (GUID) の一覧を指定Windowsインストールできません。 既定では、このポリシー設定は、デバイスのインストールWindows許可する他のポリシー設定よりも優先されます。

> [!NOTE]
> **これらのデバイス ID のいずれかに一致するデバイスのインストールを許可** し、該当するデバイスに対してこのポリシー設定を置き換えるために **、これらのデバイス インスタンス ID に一致するデバイスのインストールを許可** するポリシー設定を有効にするには、**すべてのデバイス一致条件ポリシーでデバイスインストール ポリシーを許可および禁止の評価の階層化順序を適用** するポリシー設定を有効にします。

このポリシー設定を有効にすると、デバイス セットアップ クラス GUID が作成した一覧に表示されるドライバー パッケージのインストールまたは更新がWindowsに禁止されます。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定はリモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。

このポリシー設定を無効にするか、未構成にした場合、Windows他のポリシー設定で許可または禁止されているようにデバイスをインストールおよび更新できます。

### <a name="prevent-installation-of-removable-devices"></a>リムーバブル デバイスのインストールを禁止する

このポリシー設定を使用すると、Windowsがリムーバブル デバイスをインストールできないようにすることができます。 デバイスが接続されているデバイスのドライバーが、デバイスがリムーバブルであることを示す場合、デバイスはリムーバブルと見なされます。 たとえば、ユニバーサル シリアル バス (USB) デバイスは、デバイスが接続されている USB ハブのドライバーによって取り外し可能であると報告されます。 既定では、このポリシー設定は、デバイスのインストールWindows許可する他のポリシー設定よりも優先されます。

> [!NOTE]
> **これらのデバイスセットアップ クラスに一致するドライバーを使用してデバイスのインストールを許可** する、**これらのデバイス ID のいずれかに一致するデバイスのインストールを許可** する、および該当するデバイスのこのポリシー設定を置き換えるために **、これらのデバイス インスタンス ID ポリシー設定のいずれかに一致するデバイスのインストールを許可** するには、**すべてのデバイス一致条件ポリシーのポリシー設定で、デバイスのインストール ポリシーを許可および禁止の評価の階層化順序を適用** するを有効にします。

このポリシー設定を有効にした場合、Windowsはリムーバブル デバイスをインストールできず、既存のリムーバブル デバイスはドライバーを更新できません。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定はリモート デスクトップ クライアントからリモート デスクトップ サーバーへのリムーバブル デバイスのリダイレクトに影響します。

このポリシー設定を無効にするか、未構成にした場合、Windowsは、他のポリシー設定で許可または禁止されているリムーバブル デバイスのドライバー パッケージをインストールおよび更新できます。

## <a name="common-removable-storage-access-control-scenarios"></a>リムーバブル Storage Access Controlの一般的なシナリオ

リムーバブル Storage Access ControlのMicrosoft Defender for Endpoint理解を深めるために、ユーザーが従う一般的なシナリオをいくつかまとめていきます。

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>シナリオ 1: すべての USB デバイスのインストールを禁止する一方で、承認された USB サム ドライブのみのインストールを許可する

このシナリオでは、次のポリシーが使用されます。

- これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスをインストールできないようにします。
- すべてのデバイス一致条件に対して、デバイスのインストール ポリシーを許可および禁止するための階層化された評価順序を適用します。
- これらのデバイス インスタンス ID のいずれかに一致するデバイスのインストールを許可するか、これらのデバイス ID のいずれかに一致するデバイスのインストールを許可します。

#### <a name="deploying-and-managing-policy-via-intune"></a>Intuneを使用したポリシーのデプロイと管理

デバイスのインストール機能を使用すると、Intuneを使用してデバイスにポリシーを適用できます。

#### <a name="licensing"></a>ライセンス

デバイスのインストールを開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)を確認する必要があります。 デバイスのインストールにアクセスして使用するには、Microsoft 365 E3必要があります。

#### <a name="permission"></a>アクセス許可

Intuneでのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに付与されている必要があります。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールのいずれかを使用できます。

- ポリシーとプロファイル マネージャーのロール
- または、デバイス構成プロファイルの作成/編集/更新/読み取り/削除/レポートの表示アクセス許可が有効になっているカスタム ロール
- またはグローバル管理者

#### <a name="deploying-policy"></a>ポリシーのデプロイ

Microsoft エンドポイント マネージャー [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)

1. **これらのデバイス セットアップ クラスに一致するドライバーを使用してデバイスのインストールを禁止するを構成します**。

    - Open Endpoint security > Attack surface reduction > ポリシー > プラットフォームの作成: Windows 10 (以降) & プロファイル: デバイス制御。

      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="[プロファイルの編集] ページ" lightbox="../../media/devicepolicy-editprofile.png":::

2. USB、デバイスを接続すると、次のエラー メッセージが表示されます。

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="エラー メッセージ" lightbox="../../media/devicepolicy-errormsg.png":::

3. **すべてのデバイス一致条件で、デバイスのインストール ポリシーを許可および禁止するに対して、階層化された評価順序を適用** するを有効にします。

    - **現時点では OMA-URI のみがサポート** されています: デバイス >構成プロファイル>プロファイル>プラットフォームの作成: Windows 10 (以降) & プロファイル: カスタム

      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="[行の編集] ページ" lightbox="../../media/devicepolicy-editrow.png":::

4. 許可された USB インスタンス ID を有効にして追加する – **これらのデバイス ID のいずれかに一致するデバイスのインストールを許可します**。

    - 手順 1 デバイス制御プロファイルを更新する

      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="[デバイス制御] ページの識別子" lightbox="../../media/devicepolicy-devicecontrol.png":::

    PCI\CC_0C03の追加;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST; USB\ROOT_HUB30;USB\ROOT_HUB20;上記のスクリーン キャプチャの USB\USB20_HUBは、1 つの USB サム ドライブを有効にするのに 1 つのハードウェア ID のみを有効にするだけでは十分ではないためです。 ターゲットデバイスの前にあるすべての USB デバイスがブロック (許可) されていないことを確認する必要があります。 デバイス マネージャーを開き、ビューを [接続別のデバイス] に変更して、PnP ツリーでのデバイスのインストール方法を確認できます。 この場合、ターゲット USB サム ドライブも許可されるように、次のデバイスを許可する必要があります。

    PCI\CC_0C03の追加;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST; USB\ROOT_HUB30;USB\ROOT_HUB20;上記のスクリーン キャプチャの USB\USB20_HUBは、1 つの USB サム ドライブを有効にするのに 1 つのハードウェア ID のみを有効にするだけでは十分ではないためです。 ターゲットデバイスの前にあるすべての USB デバイスがブロック (許可) されていないことを確認する必要があります。 デバイス マネージャーを開き、ビューを [接続別のデバイス] に変更して、PnP ツリーでのデバイスのインストール方法を確認できます。 この場合、ターゲット USB サム ドライブも許可されるように、次のデバイスを許可する必要があります。

    - "Intel(R) USB 3.0 eXtensible Host Controller – 1.0 (Microsoft)" -> PCI\CC_0C03
    - "USB ルート ハブ (USB 3.0)" -> USB\ROOT_HUB30
    - "汎用 USB ハブ" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="デバイス マネージャー ページの [表示] メニュー項目" lightbox="../../media/devicepolicy-devicemgr.png":::

    > [!NOTE]
    > システム内の一部のデバイスには、システムへのインストールを定義するための複数の接続レイヤーがあります。 USB サム ドライブはそのようなデバイスです。 したがって、システムでブロックまたは許可する場合は、各デバイスの接続パスを理解することが重要です。 システムで一般的に使用される一般的なデバイス ID がいくつかあり、そのような場合に "許可リスト" を構築するための適切なスタートを提供できます。 次に例を示します (すべての USB で常に同じとは限りません。デバイス マネージャーを使用して管理するデバイスの PnP ツリーを理解する必要があります)。
    >
    > PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST (ホスト コントローラー用)/USB\ROOT_HUB30;USB\ROOT_HUB20 (USB ルート ハブの場合)/USB\USB20_HUB (汎用 USB ハブの場合)/
    >
    > 特にデスクトップ マシンの場合は、キーボードとマウスが接続されているすべての USB デバイスを上記の一覧に一覧表示することが重要です。 これを行わないと、ユーザーが HID デバイスを介してマシンにアクセスできない可能性があります。
    >
    > PC の製造元によって、PnP ツリーに USB デバイスを入れ子にする方法が異なる場合がありますが、一般的に、この方法が行われます。

5. 許可されている USB をもう一度接続します。 これで許可され、使用可能になったことがわかります。

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="ドライブの削除の詳細ページ" lightbox="../../media/devicepolicy-removedrive.png":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>グループ ポリシーを使用したポリシーのデプロイと管理

デバイスのインストール機能を使用すると、グループ ポリシーを使用してポリシーを適用できます。

#### <a name="licensing"></a>ライセンス

デバイスのインストールにアクセスして使用するには、Windows E3 が必要です。

#### <a name="deploying-policy"></a>ポリシーのデプロイ

展開の詳細については、グループ ポリシー [(Windows 10) を使用したデバイス インストールの管理 - Windows クライアント](/windows/client-management/manage-device-installation-with-group-policy)を参照してください。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでデバイス コントロールのリムーバブル Storage Access Control データを表示する

[Microsoft 365 セキュリティ](https://sip.security.microsoft.com/homepage) ポータルには、Device Control Device Installation によってブロックされたリムーバブル ストレージが表示されます。 Microsoft 365セキュリティにアクセスするには、次のサブスクリプションが必要です。

- E5 レポートのMicrosoft 365

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

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="ブロック ストレージ" lightbox="../../media/block-removable-storage2.png":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>ターゲット マシンがデプロイされたポリシーを取得するかどうかを確認するにはどうすればよいですか?

次のクエリを使用して、Microsoft 365 セキュリティ ポータルでマルウェア対策クライアントのバージョンを取得できます。

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens
DeviceRegistryEvents
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\"
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>許可ポリシーが機能しない理由

1 つの USB サム ドライブを有効にするには、ハードウェア ID を 1 つだけ有効にするだけでは十分ではありません。 ターゲットデバイスの前にあるすべての USB デバイスがブロック (許可) されていないことを確認します。

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="デバイスのインストールに関する FAQ" lightbox="../../media/devicemgrscrnshot.png":::
