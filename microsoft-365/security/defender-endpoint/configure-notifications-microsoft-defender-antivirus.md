---
title: 通知Microsoft Defender ウイルス対策構成する
description: エンドポイントの標準通知と他の通知の両方を構成Microsoft Defender ウイルス対策する方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 143722108ef1c5df8432610ff372697fdd3407df
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58532525"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>エンドポイントMicrosoft Defender ウイルス対策通知を構成する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

このWindows 10、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。 Microsoft Defender ウイルス対策が完了し、脅威が検出されると、エンドポイントに通知が表示されます。 通知は、スケジュールされたスキャンと手動でトリガーされたスキャンの両方に従います。 これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。

組織のセキュリティ チームの一員である場合は、システムの再起動を求める通知や脅威が検出され修復されたという通知など、エンドポイントへの通知の表示方法を構成できます。

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>グループ ポリシーまたはアプリを使用してウイルス対策Windows セキュリティ構成する

最近の脅威検出の概要など、追加の通知の表示は、Windows セキュリティグループ ポリシー[で](microsoft-defender-security-center-antivirus.md)構成できます。

> [!NOTE]
> このWindows 10バージョン 1607 では、この機能は拡張通知と呼ばされ、[更新プログラムの更新] Windows 設定で& \> **構成** \> Windows Defender。 すべてのバージョンのグループ ポリシー設定で、Windows 10機能は拡張通知と **呼ばれる。**

### <a name="use-group-policy-to-disable-additional-notifications"></a>グループ ポリシーを使用して追加の通知を無効にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4. [管理 **用テンプレート] を選択します**。

5. ツリーを展開して **、reporting**Windowsコンポーネント** \> **Microsoft Defender ウイルス対策>** 展開します。

6. [拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。 次に [**OK**] を選びます。 これにより、追加の通知が表示されません。

> [!IMPORTANT]
> 追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>アプリを使用Windows セキュリティ通知を無効にする

1. タスク バーのWindows セキュリティをクリックするか、スタート メニューの [セキュリティ] を検索して、アプリを開 **きます**。

2. [ **ウイルス&保護** ] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] & **を選択します。**

3. [通知] セクションまで **スクロールし** 、[通知設定の **変更] を選択します**。

4. スイッチを Off または **On にスライド****して**、追加の通知を無効または有効にします。

> [!IMPORTANT]
> 追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>グループ ポリシーを使用してエンドポイントの標準通知を構成する

グループ ポリシーを使用すると、次の場合に使用できます。

- ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する
- エンドポイントのすべての通知を非表示にする
- エンドポイントで再起動通知を非表示にする

通知の非表示は、インターフェイス全体を非表示にできない状況Microsoft Defender ウイルス対策があります。 詳細[については、「ユーザーがユーザー](prevent-end-user-interaction-microsoft-defender-antivirus.md)インターフェイスを表示または操作Microsoft Defender ウイルス対策する」を参照してください。 通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。 実行する必要があるアクション (再起動など) に関連する通知は、監視ダッシュボードとレポートMicrosoft エンドポイント マネージャー Endpoint Protection[表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。 

エンドポイント通知にカスタム連絡先情報を追加するには、「組織のアプリ[Windows セキュリティカスタマイズする」を参照してください](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。

### <a name="use-group-policy-to-hide-notifications"></a>グループ ポリシーを使用して通知を非表示にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動し、[** 管理用テンプレート **] を選択します**。

4. ツリーを展開して **、WindowsインターフェイスMicrosoft Defender ウイルス対策** \>  \> **コンポーネントに展開します**。 

5. [すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。 

6. **[OK]** を選択します。 これにより、追加の通知が表示されません。

### <a name="use-group-policy-to-hide-reboot-notifications"></a>グループ ポリシーを使用して再起動通知を非表示にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して **、WindowsインターフェイスMicrosoft Defender ウイルス対策** \>  \> **コンポーネントに展開します**。

5. [再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。 

5. **[OK]** を選択します。 これにより、追加の通知が表示されません。

