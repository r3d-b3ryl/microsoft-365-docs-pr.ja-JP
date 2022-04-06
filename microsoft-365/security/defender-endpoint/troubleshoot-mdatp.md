---
title: Microsoft Defender for Endpoint サービスに関する問題のトラブルシューティング
description: サービスにアクセスしようとすると、サーバー エラーなどの既知の問題に対する解決策と回避策を見つけます。
keywords: Microsoft Defender for Endpoint、サーバー エラー、アクセス拒否、無効な資格情報、データなし、ダッシュボード ポータル、許可、イベント ビューアーのトラブルシューティング
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bcd0f5ba70d154c40972c0b8035d1617a9e71966
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665846"
---
# <a name="troubleshoot-service-issues"></a>サービスに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

このセクションでは、Microsoft Defender for Endpoint サービスを使用するときに発生する可能性がある問題に対処します。

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>サーバー エラー - 無効な資格情報が原因でアクセスが拒否されました

サービスにアクセスしようとしたときにサーバー エラーが発生した場合は、ブラウザーの Cookie 設定を変更する必要があります。
Cookie を許可するようにブラウザーを構成します。

## <a name="elements-or-data-missing-on-the-portal"></a>ポータルで見つからない要素またはデータ

一部の要素またはデータがMicrosoft 365 Defenderに見つからない場合は、プロキシ設定によってブロックされている可能性があります。

プロキシ許可リストが `*.security.microsoft.com` 含まれていることを確認します。

> [!NOTE]
> 次のエンドポイントを追加する場合は、HTTPS プロトコルを使用する必要があります。

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender for Endpoint サービスは、イベント ビューアーにイベント ログまたはエラー ログを表示します

Microsoft Defender for Endpoint サービスによって報告されるイベント ID の一覧については、「イベント ビューアーを使用してイベント[とエラーを確認](event-error-codes.md)する」を参照してください。 この記事には、イベント エラーのトラブルシューティング手順も含まれています。

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender for Endpointサービスが再起動後に開始できず、エラー 577 が表示される

デバイスのオンボードが正常に完了したが、再起動後にMicrosoft Defender for Endpointが起動せず、エラー 577 が表示される場合は、ポリシーによってWindows Defenderが無効になっていないことを確認します。

詳細については、「[ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認する](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)」を参照してください。

## <a name="known-issues-with-regional-formats"></a>地域形式に関する既知の問題

### <a name="date-and-time-formats"></a>日付と時刻の形式

時刻と日付の形式には既知の問題がいくつかあります。

次の日付形式がサポートされています。

- MM/dd/yyyy
- dd/MM/yyyy

現在、次の日付と時刻の形式はサポートされていません。

- 日付形式 yyyy/MM/dd
- 日付形式 dd/MM/yy
- yy の日付形式。 yyyy のみが表示されます。
- 時間形式 HH:mm:ss はサポートされていません (12 時間の AM/PM 形式はサポートされていません)。 24 時間形式のみがサポートされます。

### <a name="use-of-comma-to-indicate-thousand"></a>コンマを使用して 1000 を示す

数字の区切り記号としてのコンマの使用はサポートされていません。 数値をコンマで区切って 1000 を示す領域は、区切り記号としてドットを使用する場合にのみ表示されます。 たとえば、15,5K は 15.5K と表示されます。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender for Endpointテナントはヨーロッパで自動的に作成されました

Microsoft Defender for Cloudを使用してサーバーを監視すると、Microsoft Defender for Endpoint テナントが自動的に作成されます。 Microsoft Defender for Endpoint データは既定でヨーロッパに格納されます。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
- [イベント ビューアーを使用してイベントとエラーを確認する](event-error-codes.md)
