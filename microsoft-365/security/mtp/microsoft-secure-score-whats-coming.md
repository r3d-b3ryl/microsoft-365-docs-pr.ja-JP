---
title: Microsoft のセキュリティで保護されたスコアについて
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266975"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft のセキュリティで保護されたスコアについて

Microsoft のセキュリティスコアをより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。 スコアと可能な最大スコアが変わります。 ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。

最近の変更については、「 [Microsoft のセキュリティで保護されたスコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。

## <a name="march-2nd-2020"></a>2020年3月2日

### <a name="removing-improvement-actions-from-intune"></a>Intune からの改善アクションの削除

Intune から提供された Microsoft のセキュリティで保護されたスコアの改善アクションを評価した後は、組織内のデバイスのセキュリティに関する有益な表現を提供していないと判断されました。 ポリシーを重視するのではなく、デバイスの構成状態を直接評価するセキュリティ制御に移行することに取り組んでいます。

次の Intune 向上アクションが削除されます。

- Microsoft Intune モバイルデバイス管理を有効にする
- Android 用の Microsoft Intune コンプライアンスポリシーを作成する
- Android 用の Microsoft Intune コンプライアンスポリシーを作成する
- Android 用の Microsoft Intune アプリ保護ポリシーを作成する
- IOS 用 Microsoft Intune アプリ保護ポリシーを作成する
- Microsoft Intune コンプライアンスポリシーが割り当てられていないデバイスを、準拠していないとしてマークする
- IOS 用 Microsoft Intune コンプライアンスポリシーを作成する
- MacOS の Microsoft Intune コンプライアンスポリシーを作成する
- Windows 用の Microsoft Intune コンプライアンスポリシーを作成する
- Android 用の Microsoft Intune 構成プロファイルを作成する
- Android 用の Microsoft Intune 構成プロファイルを作成する
- MacOS 用の Microsoft Intune 構成プロファイルを作成する
- IOS 用 Microsoft Intune 構成プロファイルを作成する
- Windows 用 Microsoft Intune 構成プロファイルを作成する
- Microsoft Intune で拡張 jailbreak 検出を有効にする
- すべてのデバイスにパッチを適用して、ウイルス対策とファイアウォールを有効にする必要がある
- Microsoft Intune への Windows Defender ATP 統合を有効にする
- Microsoft Intune Windows 情報保護ポリシーを作成する
- すべてのデバイスに高度なセキュリティ構成を要求する
- 毎週ブロックされたデバイスのレポートを確認する

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>信頼性の高い測定要件を満たしていない改善アクションを削除する

マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。

- 監査データの記録を有効にする
- 危険かつ準拠していないシャドウ IT アプリケーションを検出する
- 環境に接続されたリスクの高い OAuth アプリケーションをブロック & アクセス許可を確認する
- SharePoint online ドキュメントライブラリのバージョン管理を設定する

### <a name="mfa-improvement-action-updates"></a>MFA 向上アクションの更新

ビジネスに適したポリシーを適用しているときに、最高レベルのセキュリティを確保するための企業の必要性を反映するために、Microsoft Secure Score は、多要素認証を中心とした3つの改善アクションを削除し、2つを追加します。

削除される3つのを次に示します。

- すべてのユーザーに多要素認証を登録する
- すべてのユーザーに MFA を必須にする
- Azure AD の特権の役割に MFA を必要とする

新しい向上アクションが追加されました。

- すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする
- 管理役割に MFA を必要とする

 これらの新しい改善アクションでは、ユーザーまたは管理者に対して複数要素認証 (MFA) をディレクトリに登録し、組織のニーズに合ったポリシーの適切なセットを確立する必要があります。 主な目標は柔軟性にありますが、すべてのユーザーと管理者が複数の要因またはリスクベースの id 確認プロンプトで認証できるようにします。 これには、スコープ決定を適用する複数のポリシーを作成するか、または Microsoft が MFA のユーザーをチャレンジするタイミングを決定するセキュリティの既定値 (3 月16日) を設定するという形をとることができます。

### <a name="removing-review-improvement-actions"></a>"レビュー" の向上アクションを削除する

セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。 測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。 1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。 改善アクションのレビューは、他の改善アクションと同じ基準として測定されるわけではありません。  

これらの理由により、レビューリズムを必要とするすべての改善アクションが一時的に削除されます。 パーツに必要な操作はありません。

## <a name="march-16th-2020"></a>2020年3月16日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>信頼性の高い測定要件を満たしていない改善アクションを削除する

マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。

- OneDrive for business でユーザーのドキュメントを保存する
- Office 365 の ATP の安全な添付ファイルポリシーを設定する
- Office 365 の安全なリンクを設定して Url を確認する
- メールボックスの委任を許可しない
- サイトおよびドキュメントの匿名ゲスト共有リンクを許可する

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD 向上アクションのセキュリティの既定のサポート

Microsoft Secure Score は、強化された操作を更新して[AZURE AD のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートします。これにより、一般的な攻撃のために事前に構成されたセキュリティ設定を使用して組織を保護することが容易になります。

次の改善アクションに影響を与えます。

- すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする
- 管理役割に MFA を必要とする
- 従来の認証をブロックするポリシーを有効にする
