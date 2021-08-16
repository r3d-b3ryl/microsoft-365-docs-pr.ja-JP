---
title: Microsoft Defender for Endpoint on Mac 用の別のモバイル デバイス管理 (MDM) システムを使用した展開
description: Microsoft Defender for Endpoint on Mac を他の管理ソリューションにインストールします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 4e12af874a3615f7325b41252fc0cecaf7993868fe3a0d41545f3c45cadb0267
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857329"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上のエンドポイント用 Microsoft Defender 用の異なるモバイル デバイス管理 (MDM) システムを使用した展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メインの [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) ページを参照してください。


## <a name="approach"></a>方法

> [!CAUTION]

> 現在、Microsoft は正式に Intune と JAMF のみをサポートし、macOS 上の Microsoft Defender for Endpoint の展開と管理を行います。 Microsoft は、以下に示す情報に関して、明示または黙示を問わず一切の保証を行いません。

組織が正式にサポートされていないモバイル デバイス管理 (MDM) ソリューションを使用している場合、これは macOS で Microsoft Defender for Endpoint を展開または実行できないという意味ではありません。

Microsoft Defender for Endpoint on macOS は、ベンダー固有の機能に依存しない。 これは、次の機能をサポートする MDM ソリューションと一緒に使用できます。

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

インストール パッケージ[](mac-install-with-jamf.md)(wdav.pkg) をポータルからダウンロードして、必要なアプリケーション パッケージの[展開Microsoft 365 Defenderします](mac-install-with-jamf.md)。

パッケージを企業に展開するには、MDM ソリューションに関連付けられている手順を使用します。

### <a name="license-settings"></a>ライセンス設定

システム構成 [プロファイルを設定します](mac-install-with-jamf.md)。 

macOS 上の Microsoft Defender for Endpoint は macOS の一部では設定、MDM ソリューションは"Custom 設定 プロファイル" と呼ぶ場合があります。

プロパティ リスト jamf/WindowsDefenderATPOnboarding.plist を使用します。これは、Microsoft 365 Defender ポータルからダウンロードされたオンボーディング[パッケージから抽出できます](mac-install-with-jamf.md)。
システムが XML 形式の任意のプロパティ リストをサポートしている場合があります。 その場合は、jamf/WindowsDefenderATPOnboarding.plist ファイルを as-is でアップロードできます。
または、最初にプロパティ リストを別の形式に変換する必要があります。

通常、カスタム プロファイルには ID、名前、またはドメイン属性があります。 この値には、正確に "com.microsoft.wdav.atp" を使用する必要があります。
MDM はこれを使用して、設定ファイルをクライアント デバイスの **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** に展開し、Defender はこのファイルを使用してオンボーディング情報を読み込む。

### <a name="kernel-extension-policy"></a>カーネル拡張機能ポリシー

KEXT またはカーネル拡張ポリシーを設定します。 Microsoft が提供するカーネル拡張機能を許可するには、チーム識別子 **UBF8T346G9** を使用します。

> [!CAUTION]
> 環境が Apple Silicon (M1) デバイスで構成されている場合、これらのコンピューターは KEXT ポリシーを使用して構成プロファイルを受け取る必要があります。
> Apple は、これらのコンピューターで KEXT をサポートしていない、このようなプロファイルの展開は M1 コンピューターで失敗します。

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

エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報を Microsoft 365 Defenderします。 次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。

- フィルターの種類: プラグイン
- プラグイン バンドル識別子: `com.microsoft.wdav`
- フィルター データ プロバイダーのバンドル識別子: `com.microsoft.wdav.netext`
- フィルター データ プロバイダーの指定要件: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- フィルター ソケット: `true`

## <a name="check-installation-status"></a>インストールの状態を確認する

クライアント [デバイスで Microsoft Defender for Endpoint](mac-install-with-jamf.md) を実行し、オンボーディングの状態を確認します。
