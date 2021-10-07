---
title: Microsoft Defender ウイルス対策
description: 組み込みのマルウェア対策とウイルス対策の保護機能である Microsoft Defender ウイルス対策を管理、構成、使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策, windows defender, マルウェア対策, scep, システム センター エンドポイント保護, システム センター構成マネージャー, ウイルス, マルウェア, 脅威, 検出, 保護, セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 585fa260452a69572f6498429f3675af22ca8479
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174641"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Windows の Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint の次世代保護の主要コンポーネントです。 この保護は、機械学習、ビッグデータ分析、脅威耐性に関する詳細な調査、Microsoft のクラウド インフラストラクチャを組み合わせて、組織内のデバイス (または、エンドポイント) を保護します。 Windows Defender ウイルス対策は Windows に組み込まれており、Microsoft Defender for Endpoint と連携して、デバイスとクラウドを保護します。

## <a name="compatibility-with-other-antivirus-products"></a>他のウイルス対策製品との互換性

デバイスで Microsoft 以外のウイルス対策/マルウェア対策製品を使用している場合は、Microsoft 以外のウイルス対策ソリューションと一緒にパッシブ モードで Microsoft Defender ウイルス対策を実行できる可能性があります。 使用するオペレーティング システムと、デバイスが Defender for Endpoint にオンボードされているかどうかによって異なります。 詳細については、「[Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>アクティブ モード、パッシブ モード、および無効モードの比較

次の表は、Microsoft Defender ウイルス対策がアクティブ モード、パッシブ モード、または無効である場合に期待される内容を示しています。

<br>

****

|モード|動作|
|---|---|
|アクティブ モード|アクティブ モードでは、Microsoft Defender ウイルス対策はデバイス上の主要なウイルス対策アプリとして使用されます。 ファイルがスキャンされ、脅威が修正され、検出された脅威が組織のセキュリティ レポートと Windows セキュリティ アプリに一覧表示されます。|
|パッシブ モード|パッシブ モードでは、Microsoft Defender ウイルス対策はデバイス上の主要なウイルス対策アプリとして使用されません。 ファイルがスキャンされ、検出された脅威が報告されますが、脅威は Microsoft Defender ウイルス対策によって修正されません。 <p> **重要**: Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint にオンボードされているエンドポイントでのみパッシブ モードで実行できます。 「[Microsoft Defender ウイルス対策をパッシブ モードで実行するための要件](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)」を参照してください。|
|無効またはアンインストール済み|無効にするかアンインストールすると、Microsoft Defender ウイルス対策は使用されません。 ファイルのスキャン、脅威の修復は行われません。 一般に、Microsoft Defender ウイルス対策を無効にしたりアンインストールしたりすることはお勧めしません。|
|

詳細については、「[Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>デバイス上の Microsoft Defender ウイルス対策の状態を確認する

デバイス上の Microsoft Defender ウイルス対策の状態を確認する場合は、Windows セキュリティ アプリや Windows PowerShell などのいくつかの方法のいずれかを使用できます。

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Windows セキュリティ アプリを使用して、Microsoft Defender ウイルス対策の状態を確認する

1. Windows デバイスで、[スタート] メニューを選択し、`Security` の入力を開始します。 次に、結果で Windows セキュリティ アプリを開きます。

2. **[ウイルスと脅威の防止]** を選択します。

3. **[ウイルスと脅威の防止設定]** で **[設定の管理]** を選択します。

設定ページにウイルス対策/マルウェア対策ソリューションの名前が表示されます。

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>PowerShell を使用して Microsoft Defender ウイルス対策の状態を確認する

1. [スタート] メニューを選択し、`PowerShell` の入力を開始します。 次に、結果で Windows PowerShell を開きます。

2. 種類 `Get-MpComputerStatus`。

3. 結果のリストで、**AMRunningMode** 行を確認します。

   - **通常** は、Microsoft Defender ウイルス対策がアクティブ モードで実行されていることを意味します。

   - **パッシブ モード** は、Microsoft Defender ウイルス対策が実行されていることを意味しますが、デバイス上の主要なウイルス対策/マルウェア対策製品ではありません。 パッシブ モードは、Microsoft Defender for Endpoint にオンボードされており、特定の要件を満たすデバイスでのみ使用できます。 詳細については、「[Microsoft Defender ウイルス対策をパッシブ モードで実行するための要件](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)」を参照してください。

   - **EDR ブロック モード** は、Microsoft Defender ウイルス対策が実行されており、Microsoft Defender for Endpoint の機能である [ブロック モードでのエンドポイントの検知と応答 (EDR)](edr-in-block-mode.md) が有効になっていることを意味します。

   - **SxS パッシブ モード** とは、Microsoft Defender ウイルス対策が別のウイルス対策/マルウェア対策製品と一緒に実行されており、[定期的なスキャンが制限されている](limited-periodic-scanning-microsoft-defender-antivirus.md)ことを意味します。

> [!TIP]
> Get-MpComputerStatus PowerShell コマンドレットの詳細については、リファレンス記事 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) を参照してください。

## <a name="get-your-antivirusantimalware-platform-updates"></a>ウイルス対策/マルウェア対策プラットフォームの更新プログラムを取得する

Microsoft Defender ウイルス対策、またはウイルス対策/マルウェア対策ソリューションを最新の状態に保つことが重要です。 Microsoft は定期的な更新プログラムをリリースして、デバイスが、新しいマルウェアや攻撃手法から保護する最新のテクノロジを備えていることを確認します。 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender ウイルス対策の管理および構成](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策を評価する](evaluate-microsoft-defender-antivirus.md)
