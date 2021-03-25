---
title: Microsoft Defender ATP for Mac 用の別のモバイル デバイス管理 (MDM) システムによる展開
description: Microsoft Defender ATP for Mac を他の管理ソリューションにインストールします。
keywords: microsoft、 defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e3a20f0a356a32eddc05b3792c0c04c23197a7b0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185697"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender for Endpoint for Mac 用に異なるモバイル デバイス管理 (MDM) システムを使用した展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、 [メインの Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) ページを参照してください。

## <a name="approach"></a>方法

> [!CAUTION]
> 現在、Microsoft oficially は、Microsoft Defender for Endpoint for Mac の展開と管理のために Intune と JAMF のみをサポートしています。 Microsoft は、以下に示す情報に関して、明示または黙示を問わず一切の保証を行いません。

組織で正式にサポートされていないモバイル デバイス管理 (MDM) ソリューションを使用している場合、Microsoft Defender for Endpoint for Mac を展開または実行できないという意味ではありません。

Microsoft Defender for Endpoint for Mac は、ベンダー固有の機能に依存しない。 これは、次の機能をサポートする MDM ソリューションと一緒に使用できます。

- 管理対象デバイスに macOS .pkg を展開します。
- 管理対象デバイスに macOS システム構成プロファイルを展開します。
- 管理デバイスで任意の管理者が構成したツール/スクリプトを実行します。

最新の MDM ソリューションの多くは、これらの機能が含まれますが、呼び出し方が異なる場合があります。

ただし、前のリストから最後の要件を満たさずに Defender を展開できます。

- 一元的な方法で状態を収集できない
- Defender をアンインストールする場合は、管理者としてクライアント デバイスにローカルでログオンする必要があります。

## <a name="deployment"></a>展開

ほとんどの MDM ソリューションでは、同様の用語を使用して macOS デバイスを管理するために同じモデルを使用します。 [JAMF ベースの展開をテンプレート](mac-install-with-jamf.md)として使用します。

### <a name="package"></a>パッケージ

Microsoft Defender [](mac-install-with-jamf.md)Security Center からダウンロードしたインストール パッケージ (wdav.pkg) を使用して、必要なアプリケーション パッケージの展開[を構成します](mac-install-with-jamf.md)。

パッケージを企業に展開するには、MDM ソリューションに関連付けられている手順を使用します。

### <a name="license-settings"></a>ライセンス設定

システム構成 [プロファイルを設定します](mac-install-with-jamf.md)。 Microsoft Defender for Endpoint for Mac は macOS の一部ではなされていないので、MDM ソリューションでは"カスタム設定プロファイル" と呼ばれる場合があります。

プロパティ リスト jamf/WindowsDefenderATPOnboarding.plist を使用します。これは [、Microsoft Defender](mac-install-with-jamf.md)セキュリティ センターからダウンロードしたオンボーディング パッケージから抽出できます。
システムが XML 形式の任意のプロパティ リストをサポートしている場合があります。 その場合は、jamf/WindowsDefenderATPOnboarding.plist ファイルを as-is でアップロードできます。
または、最初にプロパティ リストを別の形式に変換する必要があります。

通常、カスタム プロファイルには ID、名前、またはドメイン属性があります。 この値には、正確に "com.microsoft.wdav.atp" を使用する必要があります。
MDM はこれを使用して、設定ファイルをクライアント デバイスの **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** に展開し、Defender はこのファイルを使用してオンボーディング情報を読み込む。

### <a name="kernel-extension-policy"></a>カーネル拡張機能ポリシー

KEXT またはカーネル拡張ポリシーを設定します。 Microsoft が提供するカーネル拡張機能を許可するには、チーム識別子 **UBF8T346G9** を使用します。

### <a name="system-extension-policy"></a>システム拡張ポリシー

システム拡張ポリシーを設定します。 チーム識別子 **UBF8T346G9** を使用し、次のバンドル識別子を承認します。

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>フル ディスク アクセス ポリシー

次のコンポーネントにフル ディスク アクセスを付与します。

- Microsoft Defender for Endpoint
    - 識別子: `com.microsoft.wdav`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender for Endpoint Security Extension
    - 識別子: `com.microsoft.wdav.epsext`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>ネットワーク拡張ポリシー

エンドポイント検出と応答機能の一環として、Microsoft Defender for Endpoint for Mac はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。 次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。

- フィルターの種類: プラグイン
- プラグイン バンドル識別子: `com.microsoft.wdav`
- フィルター データ プロバイダーのバンドル識別子: `com.microsoft.wdav.netext`
- フィルター データ プロバイダーの指定要件: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- フィルター ソケット: `true`

## <a name="check-installation-status"></a>インストールの状態を確認する

クライアント [デバイスで Microsoft Defender for Endpoint](mac-install-with-jamf.md) を実行し、オンボーディングの状態を確認します。
