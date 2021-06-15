---
title: 通知Microsoft Defender ウイルス対策構成する
description: エンドポイントの標準通知と追加の通知の両方を構成Microsoft Defender ウイルス対策する方法について説明します。
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926240"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される通知を構成する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

このWindows 10、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。

手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。 これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。

また、再起動の通知や脅威が検出され修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される追加の通知を構成する

最近の脅威検出の概要など、追加の通知の表示は、Windows セキュリティグループ ポリシー[で](microsoft-defender-security-center-antivirus.md)構成できます。

> [!NOTE]
> このWindows 10バージョン 1607 では、この機能は拡張通知と呼ばされ、[更新プログラムの更新] Windows 設定で&  >  **構成**  >  Windows Defender。 すべてのバージョンのグループ ポリシー設定で、Windows 10拡張通知 **と呼ばれる。**

> [!IMPORTANT]
> 追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。

**追加の通知Windows セキュリティ無効にするには、次のアプリを使用します。**

1. タスク バーのWindows セキュリティをクリックするか、スタート メニューの [セキュリティ] を検索して、アプリを開 **きます**。

2. [ **ウイルス&保護** ] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] & **を選択します。**

3. [通知] セクションまで **スクロールし** 、[通知設定の **変更] をクリックします**。

4. スイッチを Off または **On にスライド****して**、追加の通知を無効または有効にします。

**グループ ポリシーを使用して、追加の通知を無効にします。**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して、[**レポートWindowsコンポーネント> Microsoft Defender ウイルス対策 >展開します**。

5. [拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

## <a name="configure-standard-notifications-on-endpoints"></a>エンドポイントの標準通知を構成する

グループ ポリシーを使用すると、次の場合に使用できます。

- ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する
- エンドポイントのすべての通知を非表示にする
- エンドポイントで再起動通知を非表示にする

通知の非表示は、インターフェイス全体を非表示にできない状況Microsoft Defender ウイルス対策があります。 詳細[については、「ユーザーがユーザー](prevent-end-user-interaction-microsoft-defender-antivirus.md)インターフェイスを表示または操作Microsoft Defender ウイルス対策する」を参照してください。 

> [!NOTE]
> 通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。 実行する必要があるアクション (再起動など) に関連する通知は、監視ダッシュボードとレポートMicrosoft エンドポイント マネージャー Endpoint Protection[表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。 

ユーザー[がコンピューターにWindows セキュリティ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)通知にカスタム連絡先情報を追加する手順については、「組織のアプリをカスタマイズする」を参照してください。

**グループ ポリシーを使用して通知を非表示にする:**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。 

4. [すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

**グループ ポリシーを使用して再起動通知を非表示にします。**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。

5. [再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策](configure-end-user-interaction-microsoft-defender-antivirus.md)
