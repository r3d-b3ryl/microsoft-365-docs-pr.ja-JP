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
ms.openlocfilehash: ffdf5cffb50d6145d6059233e0850839f4dfb582
ms.sourcegitcommit: 26b35012c42fef935d6c4a6509dde6c22a9b922a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385242"
---
# <a name="review-detected-threats-and-take-action"></a>検出された脅威を確認して対処する

悪意のあるファイルまたはソフトウェアが検出されるとすぐに、Microsoft Defender ウイルス対策によってブロックされ、実行が禁止されます。 また、クラウドで提供される保護が有効になっている場合は、新たに検出された脅威がウイルス対策およびマルウェア対策エンジンに追加されるため、他のデバイスやユーザーも保護されます。

Microsoft Defender ウイルス対策は、次の種類の脅威に対して検出および保護を行います。

- デバイス上のウイルス、マルウェア、および web ベースの脅威
- フィッシングの試行
- データ盗用の試行回数

IT プロフェッショナル/管理者は、Microsoft 365 管理センターで [Intune に登録されている Windows 10 デバイス](/mem/intune/enrollment/device-enrollment) 間の脅威検出に関する情報を表示することができます。 次のような概要情報が表示されるはずです。

- ウイルス対策保護が必要なデバイスの数
- セキュリティポリシーに準拠していないデバイスの数
- 現在アクティブ、軽減、または解決されている脅威の数

脅威の検出とデバイスに関する特定の情報を表示するには、いくつかのオプションがあります。

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の [**アクティブなデバイス**] ページ この記事の「 [アクティブなデバイス」ページで、「脅威の検出を管理する」を](#manage-threat-detections-on-the-active-devices-page) 参照してください。
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の [**アクティブな脅威**] ページ この記事の「 [アクティブな脅威の検出を管理する」ページを](#manage-threat-detections-on-the-active-threats-page) 参照してください。
- <a href="https://endpoint.microsoft.com" target="_blank">Microsoft エンドポイントマネージャー</a>の [**ウイルス対策**] ページ この記事の「 [脅威検出を管理](#manage-threat-detections-in-microsoft-endpoint-manager) する」を参照してください。

詳細については、「 [Microsoft Defender ウイルス対策によって検出された脅威](threats-detected-defender-av.md)」を参照してください。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>[ **アクティブなデバイス** ] ページで脅威の検出を管理する

次の手順は、Microsoft 365 Business Premium を持つお客様に適用されます。

1. Microsoft 365 管理センターに移動し、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> サインインします。

2. [ナビゲーション] ページで、[**デバイス** の  >  **アクティブなデバイス**] を選択します。 保護状態、ウイルス対策 (AV) 保護の状態、検出されたアクティブな脅威の数など、アクティブなデバイスと詳細の一覧が表示されます。

3. デバイスを選択すると、そのデバイスと利用可能なアクションの詳細が表示されます。 推奨事項と実行可能なアクション ( **更新ポリシー**、 **ウイルス対策の更新**、 **クイックスキャン** の実行、 **フルスキャンの実行** など) を含むフライアウトが開きます。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>[ **アクティブな脅威** ] ページで脅威検出を管理する

次の手順は、Microsoft 365 Business Premium を持つお客様に適用されます。 [Windows 10 デバイスをセキュリティで保護](/microsoft-365/business/secure-win-10-pcs) し、 [Intune に登録](/mem/intune/enrollment/windows-enrollment-methods)する必要があります。

> [!NOTE]
> **Microsoft Defender ウイルス対策** カードおよび **アクティブな脅威** ページはフェーズでロールアウトされるため、すぐにアクセスできない場合があります。

1. Microsoft 365 管理センターに移動し、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> サインインします。

2. **Microsoft Defender ウイルス対策** カードで、[**アクティブな脅威の表示**] を選択します。 (または、ナビゲーションウィンドウで [ **Health**  >  ] を選択します。**脅威 & ウイルス対策**)

3. [ **アクティブな脅威** ] ページで、検出された脅威を選択して、その詳細を調べます。 影響を受けるデバイスを含む、その脅威に関する詳細が表示されたフライアウトが開きます。

4. ポップアップで、 **更新ポリシー**、 **ウイルス対策の更新**、 **クイックスキャンの実行** など、使用可能なアクションを表示するデバイスを選択します。

## <a name="actions-you-can-take"></a>実行できるアクション

特定の脅威またはデバイスの詳細を表示すると、推奨事項と1つ以上の操作を実行できることがわかります。 次の表では、表示される可能性のあるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| 保護を構成する | 脅威保護ポリシーを構成する必要があります。 リンクを選択して、[ポリシーの構成] ページに移動します。<br><br>サポートが必要な場合 「 [Microsoft Intune でのエンドポイントセキュリティポリシーを使用してデバイスセキュリティを管理](/mem/intune/protect/endpoint-security-policy)する」を参照してください。 |
| ポリシーを更新する | ウイルス対策およびリアルタイム保護ポリシーを更新または構成する必要があります。 リンクを選択して、[ポリシーの構成] ページに移動します。<br><br>サポートが必要な場合 「 [Microsoft Intune でのエンドポイントセキュリティポリシーを使用してデバイスセキュリティを管理](/mem/intune/protect/endpoint-security-policy)する」を参照してください。 |
| クイックスキャンの実行 | レジストリキーや既知の Windows スタートアップフォルダーなど、マルウェアが登録されている可能性がある一般的な場所に焦点を絞って、デバイス上でクイックウイルススキャンを開始します。 |
| フルスキャンの実行 | デバイスで完全なウイルス対策スキャンを開始し、マルウェアが登録されている可能性のある一般的な場所に焦点を置き、デバイス上のすべてのファイルとフォルダーを含めます。 結果が [Microsoft エンドポイントマネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| ウイルス対策の更新 | ウイルス対策およびマルウェア対策保護のために、デバイスが [セキュリティインテリジェンスの更新](https://go.microsoft.com/fwlink/?linkid=2149926) を取得する必要があります。 |
| デバイスを再起動する | Windows 10 デバイスを5分以内に再起動するように強制します。<br><br>**重要:** デバイスの所有者またはユーザーには、再起動の通知が自動的に行われず、保存されていない作業が失われる可能性があります。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Microsoft エンドポイントマネージャーで脅威検出を管理する

Microsoft エンドポイントマネージャーを使用して、脅威の検出を管理することができます。 Windows 10 デバイスを Intune (Microsoft エンドポイントマネージャーの一部) [に登録](/mem/intune/enrollment/windows-enrollment-methods) する必要があります。

1. Microsoft エンドポイントマネージャー管理センターに移動し、 <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> サインインします。

2. ナビゲーションウィンドウで、[ **エンドポイントセキュリティ**] を選択します。

3. [ **管理**] で、[ **ウイルス対策**] を選択します。 **概要**、 **windows 10 の異常なエンドポイント**、 **windows 10 で検出されたマルウェア** など、いくつかのタブが表示されます。

4. 使用可能なタブの情報を確認し、必要なアクションを実行します。

たとえば、[ **Windows 10 検出されたマルウェア** ] タブにデバイスが表示されているとします。デバイスを選択すると、 **再起動**、 **クイックスキャン**、 **フルスキャン**、 **同期**、 **更新署名** など、特定のアクションが使用できるようになります。 そのデバイスのアクションを選択します。

次の表では、Microsoft エンドポイントマネージャーに表示される可能性のあるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| Restart | Windows 10 デバイスを5分以内に再起動するように強制します。<br><br>**重要:** デバイスの所有者またはユーザーには、再起動の通知が自動的に行われず、保存されていない作業が失われる可能性があります。 |
| クイックスキャン | レジストリキーや既知の Windows スタートアップフォルダーなど、マルウェアが登録されている可能性がある一般的な場所に焦点を絞って、デバイス上でクイックウイルススキャンを開始します。 結果が [Microsoft エンドポイントマネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| フルスキャン | デバイスで完全なウイルス対策スキャンを開始し、マルウェアが登録されている可能性のある一般的な場所に焦点を置き、デバイス上のすべてのファイルとフォルダーを含めます。 結果が [Microsoft エンドポイントマネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| 同期 | Intune (Microsoft エンドポイントマネージャーの一部) を使用して、デバイスをチェックインする必要があります。 デバイスがチェックインすると、デバイスには、デバイスに割り当てられている保留中のアクションまたはポリシーがすべて送信されます。 |
| 署名の更新 | ウイルス対策およびマルウェア対策保護のために、デバイスが [セキュリティインテリジェンスの更新](https://go.microsoft.com/fwlink/?linkid=2149926) を取得する必要があります。 |

> [!TIP]
> 詳細については、「 [デバイスのリモートアクション](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)」を参照してください。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>マルウェア分析のためにファイルを送信する方法

失われた、または誤ってマルウェアとして分類されたファイルがある場合は、そのファイルをマルウェア分析のために Microsoft に提出することができます。 ユーザーと IT 管理者は、分析用のファイルを送信できます。 を参照してください [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) 。
