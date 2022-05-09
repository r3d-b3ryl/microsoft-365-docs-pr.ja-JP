---
title: Mac でのMicrosoft Defender for Endpoint用の別のモバイル デバイス管理 (MDM) システムを使用した展開
description: 他の管理ソリューションに mac にMicrosoft Defender for Endpointをインストールします。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 配置, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c8ffab850302967b9e36e841bf035cef07ad2775
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767239"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpoint用の別のモバイル デバイス管理 (MDM) システムを使用した展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

作業を開始する前に、[macOS のメイン Microsoft Defender for Endpointページで](microsoft-defender-endpoint-mac.md)、現在のソフトウェア バージョンの前提条件とシステム要件の説明を参照してください。


## <a name="approach"></a>方法

> [!CAUTION]

> 現在、Microsoft では、macOS でのMicrosoft Defender for Endpointの展開と管理に関して、Intuneと JAMF のみが正式にサポートされています。 Microsoft は、以下に示す情報に関して、明示または黙示を問わず、一切の保証を行いません。

組織で公式にサポートされていないモバイル デバイス管理 (MDM) ソリューションを使用している場合、macOS でMicrosoft Defender for Endpointを展開または実行できないという意味ではありません。

macOS でのMicrosoft Defender for Endpointは、ベンダー固有の機能には依存しません。 次の機能をサポートする任意の MDM ソリューションで使用できます。

- macOS .pkg をマネージド デバイスにデプロイします。
- macOS システム構成プロファイルをマネージド デバイスに展開します。
- 管理対象デバイスで任意の管理者が構成したツール/スクリプトを実行します。

最新の MDM ソリューションには、これらの機能が含まれていますが、呼び出し方法が異なる場合があります。

ただし、前の一覧から最後の要件を満たさずに Defender for Endpoint をデプロイできます。

- 一元的な方法で状態を収集することはできません。
- Defender for Endpoint をアンインストールする場合は、管理者としてクライアント デバイスにローカルでログオンする必要があります。

## <a name="deployment"></a>展開

ほとんどの MDM ソリューションでは、macOS デバイスの管理に同じモデルが使用され、同様の用語が使用されます。 [テンプレートとして JAMF ベースのデプロイ](mac-install-with-jamf.md)を使用します。

### <a name="package"></a>パッケージ

ポータルからダウンロードしたインストール パッケージ (wdav.pkg) を使用して、[必要なアプリケーション](mac-install-with-jamf.md) パッケージ[のデプロイMicrosoft 365 Defender構成します](mac-install-with-jamf.md)。

パッケージをエンタープライズにデプロイするには、MDM ソリューションに関連付けられている手順を使用します。

### <a name="license-settings"></a>ライセンス設定

[システム構成プロファイルを設定します](mac-install-with-jamf.md)。 

macOS のMicrosoft Defender for Endpointは macOS の一部ではないため、MDM ソリューションでは "カスタム 設定 プロファイル" と呼ばれることがあります。

ポータルからダウンロードしたオンボード パッケージから抽出できるプロパティ リスト jamf/WindowsDefenderATPOnboarding.plist [Microsoft 365 Defender](mac-install-with-jamf.md)使用します。
システムでは、XML 形式の任意のプロパティ リストがサポートされている場合があります。 その場合は、jamf/WindowsDefenderATPOnboarding.plist ファイルをそのままアップロードできます。
または、最初にプロパティ リストを別の形式に変換することが必要になる場合があります。

通常、カスタム プロファイルには ID、名前、またはドメイン属性があります。 この値には正確に "com.microsoft.wdav.atp" を使用する必要があります。
MDM は設定ファイルを使用して、クライアント デバイス上の **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** に展開し、Defender for Endpoint ではこのファイルを使用してオンボード情報を読み込みます。

### <a name="kernel-extension-policy"></a>カーネル拡張ポリシー

KEXT またはカーネル拡張ポリシーを設定します。 チーム識別子 **UBF8T346G9** を使用して、Microsoft によって提供されるカーネル拡張機能を許可します。

> [!CAUTION]
> 環境が Apple シリコン (M1) デバイスで構成されている場合、これらのマシンは KEXT ポリシーを使用して構成プロファイルを受信しないでください。
> Apple はこれらのマシンで KEXT をサポートしていません。このようなプロファイルのデプロイは M1 マシンでは失敗します。

### <a name="system-extension-policy"></a>システム拡張ポリシー

システム拡張ポリシーを設定します。 チーム識別子 **UBF8T346G9** を使用し、次のバンドル識別子を承認します。

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>フル ディスク アクセス ポリシー

次のコンポーネントにフル ディスク アクセスを付与します。

- Microsoft Defender for Endpoint
    - 識別子： `com.microsoft.wdav`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender for Endpoint セキュリティ拡張機能
    - 識別子： `com.microsoft.wdav.epsext`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>ネットワーク拡張ポリシー

エンドポイントの検出と応答機能の一環として、macOS のMicrosoft Defender for Endpointはソケット トラフィックを検査し、この情報をMicrosoft 365 Defender ポータルに報告します。 次のポリシーを使用すると、ネットワーク拡張機能でこの機能を実行できます。

- フィルターの種類: プラグイン
- プラグイン バンドル識別子: `com.microsoft.wdav`
- フィルター データ プロバイダーバンドル識別子: `com.microsoft.wdav.netext`
- フィルター データ プロバイダー指定の要件: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- フィルター ソケット: `true`

## <a name="check-installation-status"></a>インストールの状態を確認する

クライアント デバイス[でMicrosoft Defender for Endpoint](mac-install-with-jamf.md)を実行して、オンボード状態を確認します。
