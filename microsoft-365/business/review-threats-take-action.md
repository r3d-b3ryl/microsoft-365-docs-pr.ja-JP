---
title: 検出された脅威を確認して対処する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Windows 10 デバイスで Microsoft Defender ウイルス対策によって検出された脅威を確認および管理する方法について説明します。
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912788"
---
# <a name="review-detected-threats-and-take-action"></a>検出された脅威を確認して対処する

悪意のあるファイルまたはソフトウェアが検出されるとすぐに、Microsoft Defender Antivirus はファイルをブロックし、実行を妨げる。 クラウドによる保護を有効にすると、新たに検出された脅威がウイルス対策エンジンとマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。

Microsoft Defender ウイルス対策は、次の種類の脅威を検出して保護します。

- デバイス上のウイルス、マルウェア、および Web ベースの脅威
- フィッシングの試行
- データ盗難の試行

IT プロフェッショナル/管理者は、Microsoft 365 管理センターの Intune に登録されている [Windows 10](/mem/intune/enrollment/device-enrollment) デバイス間の脅威検出に関する情報を表示できます。 次のような概要情報が表示されます。

- ウイルス対策保護が必要なデバイスの数
- セキュリティ ポリシーに準拠していないデバイスの数
- 現在アクティブ、軽減、または解決されている脅威の数

脅威の検出とデバイスに関する特定の情報を表示するには、いくつかのオプションがあります。

- Microsoft  365 管理センターの<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">[アクティブなデバイス] ページ</a>です。 この記事 [の「Active Devices」ページの「脅威検出の管理」](#manage-threat-detections-on-the-active-devices-page) を参照してください。
- Microsoft  365 管理センターの<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">[アクティブな脅威] ページ</a>です。 この記事 [の「アクティブな脅威」ページの「脅威検出の管理」](#manage-threat-detections-on-the-active-threats-page) を参照してください。
- Microsoft **Endpoint** Manager の <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">[ウイルス対策] ページ</a>です。 この記事 [の「Microsoft Endpoint Manager での脅威検出の管理」](#manage-threat-detections-in-microsoft-endpoint-manager) を参照してください。

詳細については [、「Microsoft Defender ウイルス対策によって検出された脅威」を参照してください](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>[アクティブ なデバイス] ページで **脅威検出を管理** する

次の手順は、Microsoft 365 Business Premium をお持ちのお客様に適用されます。

1. [Microsoft 365 管理センター] に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 、サインインします。

2. ナビゲーション ページで、[デバイスのアクティブな **デバイス]**  >  **を選択します**。 アクティブなデバイスの一覧と、保護状態、ウイルス対策 (AV) 保護状態、検出されたアクティブな脅威の数などの詳細が表示されます。

3. デバイスを選択すると、そのデバイスと使用可能なアクションの詳細が表示されます。 フライアウトが開き、ポリシーの更新、ウイルス対策の更新、クイックスキャンの実行、フルスキャンの実行など、推奨事項と使用可能なアクションが表示されます。 

## <a name="manage-threat-detections-on-the-active-threats-page"></a>[アクティブな脅威] ページで **脅威検出を管理** する

次の手順は、Microsoft 365 Business Premium をお持ちのお客様に適用されます。 [Windows 10 デバイスは、Intune でセキュリティで](./secure-win-10-pcs.md) 保護 [され、登録されている必要があります](/mem/intune/enrollment/windows-enrollment-methods)。

> [!NOTE]
> **Microsoft Defender ウイルス対策** カードと **アクティブ** な脅威ページは段階的に展開され、すぐにアクセスできない可能性があります。

1. [Microsoft 365 管理センター] に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 、サインインします。

2. Microsoft **Defender ウイルス対策カードで** 、[アクティブな脅威の **表示] を選択します**。 (または、ナビゲーション ウィンドウで [正常性] を **選択します。**  > **ウイルス対策&脅威**.)

3. [アクティブ **な脅威] ページ** で、検出された脅威を選択して詳細を確認します。 フライアウトが開き、影響を受けるデバイスなど、その脅威に関する詳細が表示されます。

4. フライアウトで、デバイスを選択して、ポリシーの更新、ウイルス対策の更新、クイック スキャンの実行など、利用可能な **アクションを表示** します。

## <a name="actions-you-can-take"></a>実行できるアクション

特定の脅威やデバイスに関する詳細を表示すると、推奨事項と実行できる 1 つ以上のアクションが表示されます。 次の表に、表示される可能性があるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| 保護の構成 | 脅威保護ポリシーを構成する必要があります。 ポリシー構成ページに移動するリンクを選択します。<br><br>サポートが必要な場合 「Microsoft [Intune のエンドポイント セキュリティ ポリシーを使用してデバイス セキュリティを管理する」を参照してください](/mem/intune/protect/endpoint-security-policy)。 |
| ポリシーを更新する | ウイルス対策ポリシーとリアルタイム保護ポリシーを更新または構成する必要があります。 リンクを選択して、ポリシー構成ページに移動します。<br><br>サポートが必要な場合 「Microsoft [Intune のエンドポイント セキュリティ ポリシーを使用してデバイス セキュリティを管理する」を参照してください](/mem/intune/protect/endpoint-security-policy)。 |
| クイック スキャンの実行 | レジストリ キーや既知の Windows スタートアップ フォルダーなど、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイスでクイック ウイルス対策スキャンを開始します。 |
| フル スキャンの実行 | デバイス上で完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所と、デバイス上のすべてのファイルとフォルダーを含む場所に注目します。 結果は Microsoft [エンドポイント マネージャーに送信されます](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| ウイルス対策の更新 | ウイルス対策およびマルウェア対策保護 [のセキュリティ インテリジェンス更新](https://go.microsoft.com/fwlink/?linkid=2149926) プログラムを取得するには、デバイスが必要です。 |
| デバイスの再起動 | Windows 10 デバイスを強制的に 5 分以内に再起動します。<br><br>**重要:** デバイスの所有者またはユーザーは自動的に再起動の通知を受け取らなく、保存されていない作業を失う可能性があります。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager で脅威検出を管理する

Microsoft Endpoint Manager を使用して脅威検出を管理できます。 Windows 10 デバイスは Intune [(Microsoft エンドポイント](/mem/intune/enrollment/windows-enrollment-methods) マネージャーの一部) に登録する必要があります。

1. [Microsoft Endpoint Manager 管理センター] に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> 、サインインします。

2. ナビゲーション ウィンドウで、[エンドポイント セキュリティ] **を選択します**。

3. [管理 **] で**、[ウイルス対策] **を選択します**。 概要、Windows 10 の不健康なエンドポイント **、Windows 10** で検出されたマルウェアなど、いくつかのタブ **が表示されます**。

4. 使用可能なタブの情報を確認し、必要な操作を実行します。

たとえば、デバイスが **[Windows 10** 検出されたマルウェア] タブに表示されるとします。デバイスを選択すると、再起動、クイック スキャン、フル スキャン、同期、または署名の更新など、特定のアクションを **使用できます**。  そのデバイスのアクションを選択します。

次の表に、Microsoft Endpoint Manager に表示される可能性があるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| Restart | Windows 10 デバイスを強制的に 5 分以内に再起動します。<br><br>**重要:** デバイスの所有者またはユーザーは自動的に再起動の通知を受け取らなく、保存されていない作業を失う可能性があります。 |
| クイック スキャン | レジストリ キーや既知の Windows スタートアップ フォルダーなど、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイスでクイック ウイルス対策スキャンを開始します。 結果は Microsoft [エンドポイント マネージャーに送信されます](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| フル スキャン | デバイス上で完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所と、デバイス上のすべてのファイルとフォルダーを含む場所に注目します。 結果は Microsoft [エンドポイント マネージャーに送信されます](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 同期 | Intune (Microsoft エンドポイント マネージャーの一部) でチェックインするデバイスが必要です。 デバイスがチェック インすると、デバイスに割り当てられている保留中のアクションまたはポリシーがデバイスに受信されます。 |
| 署名の更新 | ウイルス対策およびマルウェア対策保護 [のセキュリティ インテリジェンス更新](https://go.microsoft.com/fwlink/?linkid=2149926) プログラムを取得するには、デバイスが必要です。 |

> [!TIP]
> 詳細については、「デバイスの [リモート アクション」を参照してください](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>マルウェア分析用にファイルを送信する方法

見つからない、または誤ってマルウェアとして分類されたと思うファイルがある場合は、そのファイルをマルウェア分析のために Microsoft に提出できます。 ユーザーと IT 管理者は、分析用にファイルを提出できます。 Visit [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .