---
title: 自動調査と修復における自動化レベル
description: 自動化レベルの概要と、それらがMicrosoft Defender for Endpointでどのように機能するかを確認する
keywords: 自動, 調査, レベル, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.date: 10/22/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: e440675a46a4340e2f659b23a31b19dbab33d2c0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328163"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>自動調査および修復機能の自動化レベル

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpointの自動調査と修復 (AIR) 機能は、いくつかのレベルの自動化のいずれかに構成できます。 自動化レベルは、AIR 調査後の修復アクションが自動的に実行されるか、承認時にのみ実行されるかに影響します。

- *完全自動化* (推奨) とは、悪意のあると判断されたアーティファクトに対して修復アクションが自動的に実行されることを意味します。
- *半自動化* とは、一部の修復アクションが自動的に実行されることを意味しますが、他の修復アクションは、実行される前に承認を待ちます。 ( [オートメーションのレベルの表を参照してください](#levels-of-automation))。
- 保留中でも完了でも、すべての修復アクションは、アクション センター ([https://security.microsoft.com](https://security.microsoft.com)) で追跡されます。

> [!TIP]
> 最適な結果を得るには、 [AIR を構成](configure-automated-investigations-remediation.md)するときに完全自動化を使用することをお勧めします。 過去 1 年間に収集および分析されたデータは、完全自動化を使用している顧客が、低レベルの自動化を使用している顧客よりも 40% 高い信頼性の高いマルウェア サンプルを削除したことを示しています。 完全な自動化は、セキュリティ運用リソースを解放し、戦略的イニシアチブに集中するのに役立ちます。

## <a name="levels-of-automation"></a>オートメーションのレベル

次の表では、各レベルの自動化とその動作について説明します。

<br>

****

|オートメーション レベル|説明|
|---|---|
|**完全 - 脅威を自動的に修復する** <br> ( *完全自動化* とも呼ばれます)|完全自動化では、修復アクションが自動的に実行されます。 実行されたすべての修復アクションは、[**履歴**] タブの [[アクション センター](auto-investigation-action-center.md)] で確認できます。必要に応じて、修復アクションを元に戻すことができます。 <p> **_完全な自動化が推奨_* され、2020 年 8 月 16 日以降にデバイス グループがまだ定義されていないMicrosoft Defender for Endpointで作成されたテナントに対して既定で選択されます。*|
|**半 - 修復の承認が必要** <br> ( *半自動化* とも呼ばれます)|このレベルの半自動化では、 *修復* アクションに承認が必要です。 このような保留中のアクションは、[**保留中**] タブの [[アクション センター](auto-investigation-action-center.md)] で表示および承認できます。 <p> *このレベルの半自動化は、2020 年 8 月 16 日より前に作成されたテナントに対して既定で選択され、Microsoft Defender for Endpointではデバイス グループが定義されていません。*|
|**Semi - コア フォルダー修復の承認が必要** <br> ( *また、半自動化の一* 種)|このレベルの半自動化では、コア フォルダー内のファイルまたは実行可能ファイルに必要なすべての修復アクションに対して承認が必要です。 コア フォルダーには、**Windows** (`\windows\*`) などのオペレーティング システム ディレクトリが含まれます。 <p> 修復アクションは、他の (コア以外の) フォルダーにあるファイルまたは実行可能ファイルに対して自動的に実行できます。 <p> コア フォルダー内のファイルまたは実行可能ファイルの保留中のアクションは、 [アクション センター](auto-investigation-action-center.md)の [ **保留中]** タブで表示および承認できます。 <p> 他のフォルダー内のファイルまたは実行可能ファイルに対して実行されたアクションは、 [アクション センター](auto-investigation-action-center.md)の [ **履歴** ] タブで確認できます。|
|**Semi - 一時フォルダー以外の修復の承認が必要** <br> ( *また、半自動化の一* 種)|このレベルの半自動化では、一時フォルダー *にない* ファイルまたは実行可能ファイルに対して必要なすべての修復アクションに対して承認が必要です。 <p> 一時フォルダーには、次の例を含めることができます。 <ul><li>`\users\*\appdata\local\temp\*`</li><li>`\documents and settings\*\local settings\temp\*`</li><li>`\documents and settings\*\local settings\temporary\*`</li><li>`\windows\temp\*`</li><li>`\users\*\downloads\*`</li><li>`\program files\`</li><li>`\program files (x86)\*`</li><li>`\documents and settings\*\users\*`</li></ul> <p> 修復アクションは、一時フォルダー内のファイルまたは実行可能ファイルに対して自動的に実行できます。 <p> 一時フォルダーにないファイルまたは実行可能ファイルの保留中のアクションは、[**保留中]** タブの [[アクション センター](auto-investigation-action-center.md)] で表示および承認できます。 <p> 一時フォルダー内のファイルまたは実行可能ファイルに対して実行されたアクションは、 [アクション センター](auto-investigation-action-center.md)の [ **履歴** ] タブで表示および承認できます。|
|**自動応答なし** <br> ( *オートメーションなし* とも呼ばれます)|自動化なしでは、組織のデバイスでは自動調査は実行されません。 その結果、自動調査の結果として修復アクションが実行されたり保留中になったりすることはありません。 ただし、ウイルス対策と次世代の保護機能の構成方法によっては、 [望ましくない可能性のあるアプリケーションからの保護](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)など、他の脅威保護機能も有効になる可能性があります。 <p> *組織のデバイスのセキュリティ体制が低下するため、***自動化なし* オプションを使用することはお勧めしません**。 [オートメーション レベルを完全なオートメーション (または少なくとも半自動化) に設定することを検討してください](/microsoft-365/security/defender-endpoint/machine-groups)。|
|

## <a name="important-points-about-automation-levels"></a>オートメーション レベルに関する重要な点

- 完全な自動化は信頼性が高く、効率的で安全であることが証明されており、すべてのお客様にお勧めです。 完全な自動化により、重要なセキュリティ リソースが解放され、戦略的イニシアチブに集中できるようになります。

- Microsoft Defender for Endpointを使用して新しいテナント (2020 年 8 月 16 日以降に作成されたテナントを含む) は、既定で完全自動化に設定されます。

- セキュリティ チームが自動化レベルでデバイス グループを定義している場合、これらの設定は、ロールアウトする新しい既定の設定によって変更されません。

- 既定の自動化設定を保持することも、組織のニーズに応じて変更することもできます。 設定を変更するには、 [自動化のレベルを設定します](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpointで自動調査と修復機能を構成する](configure-automated-investigations-remediation.md)
- [アクション センターにアクセスする](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
