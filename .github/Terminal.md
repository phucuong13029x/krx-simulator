==========================================================================
=     __ __ ____ _  __    _____ _                 __      __             =
=    / //_// __ \ |/ /   / ___/(_)___ ___  __  __/ /___ _/ /_____  _____ =
=   / ,<  / /_/ /   /    \__ \/ / __ `__ \/ / / / / __ `/ __/ __ \/ ___/ =
=  / /| |/ _, _/   |    ___/ / / / / / / / /_/ / / /_/ / /_/ /_/ / /     =
= /_/ |_/_/ |_/_/|_|   /____/_/_/ /_/ /_/\__,_/_/\__,_/\__/\____/_/      =
=                                                                        =
==========================================================================

[2025-10-20 14:23:48,157] ---------------------------------------------------------------
[2025-10-20 14:23:48,157] --- KRX Simulator Initializing (Multi-Process Architecture) ---
[2025-10-20 14:23:48,157] ---------------------------------------------------------------
[2025-10-20 14:23:48,184] [SFTP] No order date configured, using current date: 20251020
[2025-10-20 14:23:48,185] [SFTP] Loading symbols from data/sftp/hsx/TRDGES0II20_20251020.TXT
[2025-10-20 14:23:49,288] [SFTP] Loading symbols from data/sftp/hnx/TRDGES0II20_20251020.TXT
[2025-10-20 14:23:51,339] [SFTP] Loaded 11860 unique symbol instances across 8 boards.
[2025-10-20 14:23:51,348] [MAIN] Session-to-Market map successfully built
[2025-10-20 14:23:51,348] [FIX Gateway] FIX Application (Gateway) initialized.
[2025-10-20 14:23:51,349] [MARKET] Initial market status is: PREOPEN
[2025-10-20 14:23:51,350] [MARKET] Market Status Manager started.
[2025-10-20 14:23:51,355] [FIX Gateway] Session created: FIX.4.4:KRXSIMHSX->HSX_TRADING
[2025-10-20 14:23:51,356] [MAIN] Acceptor for trading_hsx created.
[2025-10-20 14:23:51,359] [FIX Gateway] Session created: FIX.4.4:KRXSIMHNX->HNX_TRADING
[2025-10-20 14:23:51,361] [MAIN] Acceptor for trading_hnx created.
2025-10-20 14:23:51,737 - 23147 - HSX - INFO - Worker process (PID: 23147) started.
[2025-10-20 14:23:51,769] [WORKER HSX] OrderProcessor has been initialized.
[2025-10-20 14:23:52,066] [FIX Gateway] Report sender thread started.
[2025-10-20 14:23:52,066] ---------------------------------------------------------------
[2025-10-20 14:23:52,066] ---        Simulator Running. Press Ctrl+C to stop.         ---
[2025-10-20 14:23:52,066] ---------------------------------------------------------------
2025-10-20 14:23:52,068 - 23150 - HNX - INFO - Worker process (PID: 23150) started.
[2025-10-20 14:23:52,086] [WORKER HNX] OrderProcessor has been initialized.
[2025-10-20 14:24:36,828] [FIX Gateway] Logon: FIX.4.4:KRXSIMHSX->HSX_TRADING
[2025-10-20 14:26:16,808] [FIX Gateway] Rejecting New Order 1760970276762: [FIX] Market is PREOPEN. Cannot place new order.
[2025-10-20 14:26:29,016] [FIX Gateway] Rejecting New Order 1760970276763: [FIX] Market is PREOPEN. Cannot place new order.
[2025-10-20 14:26:44,835] [FIX Gateway] Rejecting New Order 1760970276764: [FIX] Market is PREOPEN. Cannot place new order.
[2025-10-20 14:30:00,445] [MARKET] Market status changed to: ATO
[2025-10-20 14:30:08,001] [FIX Gateway] Queued order 1760970276765 for market HSX
2025-10-20 14:30:08,002 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276765', 'symbol': 'VN000000VPH3', 'side': '2', 'ord_type': '2', 'qty': 100.0, 'price': 4850.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 30, 8, 1361, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:30:08,002] [WORKER HSX] Reject command 1760970276765: BoardID 'G1' not allowed in session 'ATO'.
[2025-10-20 14:30:08,004] [FIX Gateway] Sent ER for 1760970276765, Status: 8
[2025-10-20 14:30:08,004] [FIX Gateway] Removed context for terminal order 1760970276765
[2025-10-20 14:30:17,774] [FIX Gateway] Queued order 1760970276766 for market HSX
2025-10-20 14:30:17,775 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276766', 'symbol': 'VN000000VPH3', 'side': '1', 'ord_type': '2', 'qty': 100.0, 'price': 4840.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 30, 17, 774141, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:30:17,775] [WORKER HSX] Reject command 1760970276766: BoardID 'G1' not allowed in session 'ATO'.
[2025-10-20 14:30:17,776] [FIX Gateway] Sent ER for 1760970276766, Status: 8
[2025-10-20 14:30:17,776] [FIX Gateway] Removed context for terminal order 1760970276766
[2025-10-20 14:31:00,462] [MARKET] Market status changed to: CONTINUOUS
[2025-10-20 14:31:33,205] [FIX Gateway] Queued order 1760970276767 for market HSX
2025-10-20 14:31:33,206 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276767', 'symbol': 'VN000000VPH3', 'side': '2', 'ord_type': '2', 'qty': 100.0, 'price': 4850.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 31, 33, 205237, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:31:33,207] [FIX Gateway] Sent ER for 1760970276767, Status: 0
[2025-10-20 14:31:39,126] [FIX Gateway] Queued order 1760970276768 for market HSX
2025-10-20 14:31:39,127 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276768', 'symbol': 'VN000000VPH3', 'side': '1', 'ord_type': '2', 'qty': 100.0, 'price': 4840.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 31, 39, 126427, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:31:39,129] [FIX Gateway] Sent ER for 1760970276768, Status: 0
[2025-10-20 14:31:44,176] [FIX Gateway] Queued order 1760970276769 for market HSX
2025-10-20 14:31:44,177 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276769', 'symbol': 'VN000000VPH3', 'side': '2', 'ord_type': '2', 'qty': 100.0, 'price': 4850.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 31, 44, 175524, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:31:44,178] [FIX Gateway] Sent ER for 1760970276769, Status: 0
[2025-10-20 14:31:49,173] [FIX Gateway] Interpreted MKT order 1760970276770 with TIF=9 as internal MTL order (K).
[2025-10-20 14:31:49,174] [FIX Gateway] Queued order 1760970276770 for market HSX
2025-10-20 14:31:49,175 - 23147 - HSX - INFO - Request received: NEW_ORDER - {'id': '1760970276770', 'symbol': 'VN000000VPH3', 'side': '1', 'ord_type': 'K', 'qty': 500.0, 'price': 0.0, 'account': 'XXXX123456', 'board_id': 'G1', 'time': datetime.datetime(2025, 10, 20, 21, 31, 49, 174031, tzinfo=<DstTzInfo 'Asia/Ho_Chi_Minh' +07+7:00:00 STD>)}
[2025-10-20 14:31:49,175] [ENGINE] MTL order 1760970276770 partially filled. Converting remainder to LO @ 4850.0.
[2025-10-20 14:31:49,176] [FIX Gateway] Sent ER for 1760970276770, Status: 0
[2025-10-20 14:31:49,177] [FIX Gateway] Sent ER for 1760970276770, Status: 1
[2025-10-20 14:31:49,178] [FIX Gateway] Sent ER for 1760970276767, Status: 2
[2025-10-20 14:31:49,178] [FIX Gateway] Removed context for terminal order 1760970276767
[2025-10-20 14:31:49,179] [FIX Gateway] Sent ER for 1760970276770, Status: 1
[2025-10-20 14:31:49,180] [FIX Gateway] Sent ER for 1760970276769, Status: 2
[2025-10-20 14:31:49,180] [FIX Gateway] Removed context for terminal order 1760970276769
[2025-10-20 14:31:49,181] [FIX Gateway] Sent ER for 1760970276770, Status: 1
[2025-10-20 14:31:59,009] [FIX Gateway] Queued cancel for 1760970276770 (New ClOrdID: 1760970276771) in HSX
2025-10-20 14:31:59,009 - 23147 - HSX - INFO - Request received: CANCEL_ORDER - {'orig_cl_ord_id': '1760970276770', 'id': '1760970276771', 'symbol': 'VN000000VPH3'}
[2025-10-20 14:31:59,011] [FIX Gateway] Sent ER for 1760970276770, Status: 4
[2025-10-20 14:31:59,011] [FIX Gateway] Removed context for terminal order 1760970276770
[2025-10-20 14:32:23,479] [FIX Gateway] Logout: FIX.4.4:KRXSIMHSX->HSX_TRADING
